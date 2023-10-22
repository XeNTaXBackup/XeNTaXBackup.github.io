## Post #1
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2017-03-17T19:38:11+00:00
- Post Title: Nier Automata

Platinum is using CriWare's "cpk" archive format again.

Can be easily opened with [https://github.com/wmltogether/CriPakTools](https://github.com/wmltogether/CriPakTools)

Contains the usual dat and dtt and so forth just like some of their other games though some things might be updated.

I was able to extract textures but some are somewhat "corrupted"(or are just aux data like directional lightmaps)




Sample file: [https://transfer.sh/13foZS/um2140.dat](https://transfer.sh/13foZS/um2140.dat)

There's some other file formats contained that could be mapped out. Some of the CPKs contain a lot of wd_ files(world data. Much of it procedurally generated using Simplygon with not much else going on.

data012.cpk contains a lot of quest and scripting data and the licenses involve a lot of ruby so there might be a huge repo of ruby scripts somewhere among the assets.

the .z files found within the .dat files are predictably zlib. An example of a decompressed "q171_hap.z" file found within "q171.dat" which is within "data012.cpk"(so many nested levels of files...)
[http://pastebin.com/raw/0rJZ4CKH](http://pastebin.com/raw/0rJZ4CKH)

pak files are pretty much containers for multiple zip streams.

Found all around the archives are what looks like "compiled" ruby code. Constants and some signs of syntax are exposed here and there. Probably pre-lexicographed ruby code to avoid storing pure plaintext.

Very likely it's just pre-compiled mruby VM bytecode output from mrbc.
[https://raw.githubusercontent.com/mruby ... y/opcode.h](https://raw.githubusercontent.com/mruby/mruby/2cbbeba0e091e95bc8456c29f6cab2c36b44a86b/include/mruby/opcode.h)

Bin files found in quest data such as 'q171_12f2963a_scp.bin' is for sure output from mrbc. (the ones with the `RITE0003` header)
[https://github.com/mruby/mruby/blob/08a ... dump.h#L53](https://github.com/mruby/mruby/blob/08a1dd2ac89333bd928a3300f712d1a7fb57e8ff/include/mruby/dump.h#L53)

Some of the middleware that Nier uses:
[https://github.com/mruby/mruby](https://github.com/mruby/mruby)
[https://github.com/antimon2/enumerable_ ... /README.md](https://github.com/antimon2/enumerable_lz/blob/master/README.md)
[https://www.musl-libc.org/](https://www.musl-libc.org/)
[http://rake.rubyforge.org/](http://rake.rubyforge.org/)
[https://github.com/yhara/enumerable-lazy](https://github.com/yhara/enumerable-lazy)
[https://www.simplygon.com/](https://www.simplygon.com/)
[http://www.geomerics.com/enlighten/](http://www.geomerics.com/enlighten/)

Made a quick extractor for the .dat file files.
[https://gist.github.com/Wunkolo/213aa61 ... ebb8ab89c2](https://gist.github.com/Wunkolo/213aa61eb0c874172aec97ebb8ab89c2)
## Post #2
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2017-03-18T21:34:48+00:00
- Post Title: Nier Automata

Model format ".wmb" has been changed. Magic is "WMB3" which is weird because some of their older games used "WMB4". Format uses a deeply nested table format similar to WMB4 somewhat. Seems to include a full map of uniform data(passed to the shader) and parameters and such. Material parameters are all floats where applicable and zero otherwise(such as for texture inputs). Header is 0x90 bytes. Writing a reader for it now while I map out all the table types and I'll use something like fbxsdk to write an exporter most likely.

Some sample wmb files
[https://transfer.sh/gSpXc/sample.zip](https://transfer.sh/gSpXc/sample.zip)
## Post #3
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-03-18T22:38:13+00:00
- Post Title: Nier Automata

Glad to see folks working on this game. Have you seen (or already taking part in) the thread on the facepunch forums for Nier? They've been discussing and working on the format a bit. If you haven't seen it, here's the link

[https://facepunch.com/showthread.php?t=1557100](https://facepunch.com/showthread.php?t=1557100)

Looking forward to progress
## Post #4
- Username: SkacikPL
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Oct 28, 2014 2:51 pm
- Post datetime: 2017-03-18T23:06:00+00:00
- Post Title: Nier Automata

So as far as my comprehension goes dtt format is basically DDS embedded with some sort of overhead?
I'm looking into it cause some of the textures could really use some high definition love.
## Post #5
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2017-03-18T23:25:06+00:00
- Post Title: Nier Automata

> Reply from ssringo
>
> Glad to see folks working on this game. Have you seen (or already taking part in) the thread on the facepunch forums for Nier? They've been discussing and working on the format a bit. If you haven't seen it, here's the link

https://facepunch.com/showthread.php?t=1557100

Looking forward to progress

The WMB format is entirely different from anything any tool out there uses. It's a new format specifically for the new rendering engine they have set up and it's entirely different from the most recent "WMB" iteration seen here([http://pastebin.com/CEHriQBv](http://pastebin.com/CEHriQBv)) which is what most tools out there use and are totally incompatible with the latest format. Here's a snippet from the reader I am working on right now. Lots of metaprogramming elsewhere as this is just a small snippet but this is very likely to be what Platinum games internally does as well. Commented with some of my research notes.  I pretty much mapped out the Materials/Uniform parameters(values that get passed to the shader) among other things. 2B's internal name is pl0000 even in the ruby bytecode.

```
struct TableReference
{
	typedef EntryType ElementType;
	std::uint32_t Offset;
	std::uint32_t Count;
};

struct Header
{
	std::uint32_t Magic; // WMB3
	std::uint32_t Unknown4; // Version?

	std::uint32_t Unknown8; // 0

	std::uint16_t UnknownC; // 0x0, 0xA
	std::uint16_t UnknownE; // 0xffff

	Vector3 UnknownVector10;
	Vector3 UnknownVector1C;

	TableReference<UnknownTable28Entry> UnknownTable28; // Table of 0x60 byte structures

	TableReference<std::uint8_t> UnknownTable30; // Table of 1 byte structures

	TableReference<UnknownTable38Entry> UnknownTable38; // Table of 0x30 byte structures

	TableReference<void> UnknownTable40; // Table of 0x20 byte structures

	TableReference<void> LODTable; // Table of 0x1C byte structures

	TableReference<void> UnknownTable50; // Often Zero

	TableReference<std::uint32_t> UnknownTable58;

	TableReference<
		TableReference<std::uint16_t>
	> UnknownTable60; // Table of... Table References to tables of uint16_t

	TableReference<MaterialParamTableEntry> MaterialParamTable; // Table of 0x30 byte structures

	TableReference<UnknownTable70Entry> UnknownTable70; // Table of 0x30 byte structures

	TableReference<void> UnknownTable78; // Table of {uint32_t Zero, uint32_t Unknown } structures
};

```


That person is using Ninjaripper which basically middle-mans between the game and directx driver so it won't have a lot of the auxiliary information to get things like rigging and texture names and so forth.


> Reply from SkacikPL
>
> So as far as my comprehension goes dtt format is basically DDS embedded with some sort of overhead?
I'm looking into it cause some of the textures could really use some high definition love.

DTT files are DAT files intended to store texture(.wtp) and model(.wmb) data among others(bxm,mot,sop,etc). .wtp files are regular DirectX textures(.dds) and can simply be renamed to a .dds extension.
## Post #6
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2017-03-19T01:52:07+00:00
- Post Title: Nier Automata

Current structure so far:

```
#include <cstdint>
#include <cstddef>

namespace WMB
{
#pragma pack(push, 1)

template<size_t Dimension>
struct Vector
{
	std::float_t f32[Dimension];
};

using Vector4 = Vector<4>;
using Vector3 = Vector<3>;
using Vector2 = Vector<2>;

template< typename EntryType >
struct TableReference
{
	typedef EntryType ElementType; // For reading functions
	std::uint32_t Offset;
	std::uint32_t Count;
};

struct StringReference
{
	std::uint32_t Offset; // Offset for null-terminated string
};

struct UnknownTable28Entry
{
	struct
	{
		// Probably Very wrong
		Vector4 UnknownVector0;
		Vector2 UnknownVector10;
		Vector2 UnknownVector18;
	} Elements[3];
};

struct GeoStreamTableEntry
{
	struct UnknownTable0Entry
	{
		Vector3 UnknownVector0; // Position?
		Vector2 UnknownVectorC; // UV?

		std::uint32_t Unknown18; // Zero
		std::uint32_t Unknown1C;
	};

	TableReference<UnknownTable0Entry> UnknownTable0; // Possible vertex stream

	TableReference<void> UnknownTable8; // Tends to be 0

	std::uint32_t VertexStride10; // Stride for UnknownTable0?
	std::uint32_t VertexStride14; // Stride

	TableReference<void> UnknownTable18; // Tends to be 0

	std::uint32_t Unknown20; // Vertex Count?
	std::uint32_t Unknown24;
	TableReference<void> IndexTable28; // Possible indice array
};

struct MaterialParamTableEntry
{
	std::uint32_t Unknown0;
	std::uint16_t Unknown4;
	std::uint16_t Unknown6;

	StringReference ParamMeshName; // Null Terminated String (ex: PL_0000_Eye)
	StringReference ParamMeshClass; // Null Terminated String (ex: Eye00_XXXXX)
	StringReference ParamsName; // Null Terminated String (ex: Default)

	std::uint32_t Unknown14; // Usually 1

	struct ParamTableEntry
	{
		StringReference UniformName; // Null terminated (ex: g_AlbedoMap)
		std::float_t Unknown4; // Uniform Value(float, 0 if not applicable such as for a texture)
	};

	TableReference<ParamTableEntry> ParamTable;

	struct UnknownTable20Entry
	{
		std::uint32_t Unknown0; // (ex: 0, 2)
		std::uint32_t Unknown4; // (ex: 2DA470h, FFFFFFFFh)
	};

	TableReference<UnknownTable20Entry> UnknownTable20;

	TableReference<ParamTableEntry> VertexShaderParamTable;

	// Same structure as "ParamTableEntry" above
	// (ex: Binormal0, Color0, Normal, Position, Tangent, TexCoord0,
	//      g_AlbedoColor_X, g_ReflectionIntensity, g_Metallic, etc )
};

struct MeshGroupTableEntry
{
	StringReference GroupName; // (ex: Body)

	Vector3 UnknownVector4;
	Vector3 UnknownVector10;

	// Possibly face indexes
	TableReference<std::uint16_t> UnknownTable1C; // Table uint16_t
	TableReference<std::uint16_t> UnknownTable24; // Table of uint16_t
};

struct UnknownTable78Entry
{
	std::uint32_t Unknown0; // 0x0
	std::uint32_t UnknownIndex4;
};

///////////////////////////////////////////////////////////////////////////////

struct Header
{
	std::uint32_t Magic; // WMB3
	std::uint32_t Unknown4; // Version?

	std::uint32_t Unknown8; // 0

	std::uint16_t UnknownC; // 0x0, 0xA
	std::int16_t UnknownE; // 0xffff

	Vector3 UnknownVector10;
	Vector3 UnknownVector1C;

	TableReference<UnknownTable28Entry> BoneTable28; // Table of 0x60 byte structures

	TableReference<std::int8_t> UnknownTable30; // Table of 1 byte structures

	TableReference<GeoStreamTableEntry> GeoStreamTable38; // Table of 0x30 byte structures

	TableReference<void> UnknownTable40; // Table of 0x20 byte structures

	// Possibly LOD related
	TableReference<void> UnknownTable48; // Table of 0x1C byte structures

	TableReference<void> UnknownTable50; // Zero

	TableReference<std::uint32_t> UnknownTable58; // Table of uint_32

	TableReference<
		TableReference<std::uint16_t>
	> UnknownTable60; // Table of... Table References to tables of uint16_t

	TableReference<MaterialParamTableEntry> MaterialParamTable; // Table of 0x30 byte structures

	// Named/Grouped chunks of geometry
	TableReference<MeshGroupTableEntry> MeshGroupTable; // Table of 0x30 byte structures

	TableReference<UnknownTable78Entry> UnknownTable78; // Table of { uint32_t Zero, uint32_t Unknown } structures

	TableReference<void> UnknownTable80; // Zero
	TableReference<void> UnknownTable88; // Zero
};

#pragma pack(pop)
}

```
## Post #7
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-03-19T15:42:34+00:00
- Post Title: Nier Automata

Good work...
Anyway this [https://gist.github.com/Wunkolo/213aa61 ... ebb8ab89c2](https://gist.github.com/Wunkolo/213aa61eb0c874172aec97ebb8ab89c2)
Have any code to recreate the .dat? i'm not a c++ dev so i can't understand the format... only the header struct...
## Post #8
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2017-03-19T18:58:57+00:00
- Post Title: Nier Automata

> Reply from marcussacana
>
> Good work...
Anyway this https://gist.github.com/Wunkolo/213aa61 ... ebb8ab89c2
Have any code to recreate the .dat? i'm not a c++ dev so i can't understand the format... only the header struct...

Added a markdown file to the gist link that describes the format a bit that should help. A "union" is basically a struct in which all the data overlaps each other so "ExtentionTableEntry" is just four bytes long. The offsets seem file-relative but you could also just load the entire file into memory and just use those same offsets as indexes in a byte array.

I haven't had the need to write an injector since you would also have to write a cpk injector which is something no one has really wanted to take on.
## Post #9
- Username: KazukiMutou
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 13, 2014 6:05 am
- Post datetime: 2017-03-19T20:22:19+00:00
- Post Title: Nier Automata

Do you happen to know in which cpk the music is stored?
## Post #10
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-03-20T01:43:04+00:00
- Post Title: Nier Automata

Okay, i extracted the data009.cpk, extracted the "subtitle\subtitle1270_us.dat" (contains new game cutscene subtitle)
After this, i translated and recreated the .dat without problem... and i patch the .cpk... but
WTF the text don't change.... i confirm if the old text contains in the new data009.cpk but yes, not found... i have sure the tools works and the file has been edited, but the game don't change anything... probabbly have the file in another packget/folder, anyone found the correct file?
## Post #11
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-03-20T02:59:03+00:00
- Post Title: Nier Automata

Okay, after analyze more i see, this subtitle files from data009.cpk it's from the demo cutscene when you don't move the mouse in main menu...
looks i need found the correct file... :/
## Post #12
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-03-20T04:00:09+00:00
- Post Title: Nier Automata

Okay, the text is in data002.cpk\ph1\p100.dat\p100_fa238e7c_scp.bin... this RITE0003 format... don't have any tool to edit he?
## Post #13
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2017-03-20T04:16:17+00:00
- Post Title: Nier Automata

> Reply from marcussacana
>
> Okay, the text is in data002.cpk\ph1\p100.dat\p100_fa238e7c_scp.bin... this RITE0003 format... don't have any tool to edit he?

"RITE0003" files are pre-compiled ruby code. Nier uses an internal virtual machine that runs [Ruby](https://www.ruby-lang.org/en/) code using a library called [mRuby](https://github.com/mruby/mruby) which is able to compile ruby source code into a binary form so the ruby source code:

```

```

would compile to this after running it through mrbc

```
    0000010: 545a 3030 3030 4952 4550 0000 003f 3030  TZ0000IREP...?00
    0000020: 3030 0000 0037 0001 0004 0000 0000 0004  00...7..........
    0000030: 0080 0006 0100 003d 0080 00a0 0000 004a  .......=.......J
    0000040: 0000 0001 0000 0348 6579 0000 0001 0004  .......Hey......
    0000050: 7075 7473 0045 4e44 0000 0000 08         puts.END.....

```


which is just [mruby VM bytecode](https://raw.githubusercontent.com/mruby/mruby/2cbbeba0e091e95bc8456c29f6cab2c36b44a86b/include/mruby/opcode.h)

unless you write a decompiler or disassembler for the bytecode then you probably won't be editing it easily.
## Post #14
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-03-20T04:50:51+00:00
- Post Title: Nier Automata

yeah... so, i found this git [https://github.com/xxuejie/mruby-bytecode](https://github.com/xxuejie/mruby-bytecode)
and this [https://github.com/yamanekko/mrb_parser](https://github.com/yamanekko/mrb_parser)
this can help...? (i don't know how to use ruby... mrb_parse looks more easy to use)
learn about the ruby VM to translate a game... shit...  I wait the lucky to see anyone develops a tool at least to edit the text

and to anyone like continue this research: 
My Stuff with Stable CPK/DAT Unpacker/Repacker - [https://www.mediafire.com/?op28t19b91ot4j7](https://www.mediafire.com/?op28t19b91ot4j7)
## Post #15
- Username: SirZephy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 21, 2017 10:06 am
- Post datetime: 2017-03-21T02:41:57+00:00
- Post Title: Nier Automata

> Reply from KazukiMutou
>
> Do you happen to know in which cpk the music is stored?

From what I could tell and my limited knowledge, the music isn't stored in the .cpk archives.
/data/sound/stream is where you can find the .wem and .wsp files, I used ww2ogg.exe and revorb.exe with a .bat script to convert.

I'm completely new to this really and am just messing about at this point to see what works, don't crucify me lol. 
I wasn't sure about the .wsp files at first, even after an extended period of google searching so I just modified the .bat to convert .wsp instead of .wem and to my surprise, it worked. however, these .wsp files/archives are at least 30MB large and are being converted down to 2-5MB audio files so I'm not sure if these .wsp files contain more than one audio file in them? I'm hoping someone more experienced can have a bit of a look to check it out.

For those wanting to know what I did precisely,

1. [Download the latest ww2ogg release](https://github.com/hcs64/ww2ogg/releases) from the Github repo (024)
2. [Download revorb.exe](http://yirkha.fud.cz/progs/foobar2000/revorb.exe) 
3. Unzip ww2ogg and drag "ww2ogg.exe" and "packed_codebooks_aoTuV_603.bin" to a new folder. Put "Revorb.exe" into the same folder
4. Create a plain text file in that folder, rename it to convert.bat (whatever suits you, as long as it's .bat) 
5. Edit the .bat and use the following for .wsp files (change the first line with (*.wsp) to (*.wem) for the .wem files)

```
pause
for %%f in (*.ogg) do revorb.exe %%f
pause
```

6. Copy the .wsp and .wem files into that folder and run the batch, press a key after it finishes the first time so it starts the revorb section of the batch and then once again to close and now you can listen to the files.

Only one file "5731267.wem" has glitch like sounds but I'm guessing that it is quite literally part of the game, just remember to turn your speaker/headphone volume down as it's quite loud. Obviously this is far from the full collection of audio files but it's a start I guess from a total noob at this stuff.

"BGM_*" - Background/music tracks, the juicy stuff, obviously. However I'm not finding any of the more noticeable tracks that I've heard so far in the game.
"core_*_" - Various small sounds for interaction with the world etc.
"p100_0_" - Sounds of metal/wood objects being shifted
"p100_2_, p200_0_ & p300_0_" - Wind/Aircraft sounds
"plffff_1_" - Louder aircraft sound
"r150_0_" - Earth rumbling sound?
## Post #16
- Username: yarrmateys
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 20, 2012 9:41 am
- Post datetime: 2017-03-22T11:03:13+00:00
- Post Title: Re: Nier Automata

> Reply from SirZephy
>
> however, these .wsp files/archives are at least 30MB large and are being converted down to 2-5MB audio files so I'm not sure if these .wsp files contain more than one audio file in them?
yeah, they do. they contain multiple file headers. they probably need to be split first.

edit: a quickbms script to do it.

```
do
    goto OFFSET
    get DUMMY long
    findloc NEXT_OFFSET string "RIFF" 0 ""
    if NEXT_OFFSET == ""
        get SIZE asize
    else
        math SIZE = NEXT_OFFSET
    endif
    math SIZE -= OFFSET
    log "" OFFSET SIZE
    math OFFSET = NEXT_OFFSET
while NEXT_OFFSET != ""

```

just select every wsp file when it asks you for source, it'll output every file's contents into separate folders.

if you combine all the wem and wsp files into one using copy /b command, it'll be even easier. the single file that'll result from that will output everything inside of it in an ordered way into the same folder without any need for messing with moving, folders, files, filenames and such.

after combining this with your stuff i got over 400 files out of it.
## Post #17
- Username: atvaark
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Aug 28, 2015 10:19 pm
- Post datetime: 2017-03-22T12:00:27+00:00
- Post Title: Re: Nier Automata

The .wsp archives can contain multiple .wem files and so can the .bnk archives.
The .wsp files don't have an index, they are just a stream of files without metadata and with alignment.

All .wem files can be extracted by parsing all the sound files (they start with the RIFF header). But ww2ogg is pretty strict about file sizes. Next to the RIFF header is the 32 bit size of the following sound file, so they can be split properly. I might upload a tool or script to split the files some time later.
I also found some .wem files in the .bnk files that overlap and can't be converted by ww2ogg.

Edit:
I managed to repair one of the corrupt .wem files inside the .bnk archive by fixing the "RIFF" header size and the "data" size. It was the first 15KB of the song "Birth of a Wish". Turns out the full size .wem file was in one of the .wsp archives.

Edit:
Here's the tool I wrote to extract all the .wem files which are not corrupt from the game's sound directory.
14997 total files can be extracted and 14974 of them can be converted to ogg via ww2ogg.

Download:
[https://gist.github.com/Atvaark/680d189 ... ractor.zip](https://gist.github.com/Atvaark/680d189c0f35acc0f1eb4a14519eba6a/raw/eb1ba9a20d5b140a96ba0e48cbee21d258416632/nier-sound-extractor.zip)

Usage example: 

```
nier-sound-extractor.exe extract -out "outdir" "E:\Games\Steam_Library\SteamApps\common\NieRAutomata\data\sound"
```
## Post #18
- Username: delguoqing
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 12, 2014 9:55 am
- Post datetime: 2017-03-23T03:42:43+00:00
- Post Title: Re: Nier Automata

good work!  Thanks for your information, that helps me a lot.
I'm trying to rip models. My script works for most wmb files except pl000. 
I'm missing 2B's lower leg. can't find out why. any ideas?



微信截图_20170323114135.png (131.8 KiB) Viewed 1007 times
## Post #19
- Username: xrb936
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 23, 2017 1:48 pm
- Post datetime: 2017-03-23T05:52:28+00:00
- Post Title: Re: Nier Automata

Hi everyone,

I am trying to make a localization for my language, do you guys know where all texts stored? I don't really know which file is correct.

Thank you!
## Post #20
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2017-03-23T07:48:42+00:00
- Post Title: Re: Nier Automata

> Reply from xrb936
>
> Hi everyone,

I am trying to make a localization for my language, do you guys know where all texts stored? I don't really know which file is correct.

Thank you!
[https://yadi.sk/d/3MsyUHRK3G79GN](https://yadi.sk/d/3MsyUHRK3G79GN)
## Post #21
- Username: xrb936
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 23, 2017 1:48 pm
- Post datetime: 2017-03-23T08:49:28+00:00
- Post Title: Re: Nier Automata

> Reply from makcar
>
> xrb936 wrote:Hi everyone,

I am trying to make a localization for my language, do you guys know where all texts stored? I don't really know which file is correct.

Thank you!
https://yadi.sk/d/3MsyUHRK3G79GN

Could you please explain me how you extracted? I am a newbie... THX!
## Post #22
- Username: xrb936
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 23, 2017 1:48 pm
- Post datetime: 2017-03-23T09:03:30+00:00
- Post Title: Re: Nier Automata

> Reply from marcussacana
>
> Okay, i extracted the data009.cpk, extracted the "subtitle\subtitle1270_us.dat" (contains new game cutscene subtitle)
After this, i translated and recreated the .dat without problem... and i patch the .cpk... but
WTF the text don't change.... i confirm if the old text contains in the new data009.cpk but yes, not found... i have sure the tools works and the file has been edited, but the game don't change anything... probabbly have the file in another packget/folder, anyone found the correct file?

How do you recreate the dat file? Is there any tool or script? Thanks.
## Post #23
- Username: Voye
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 24, 2017 8:09 am
- Post datetime: 2017-03-24T00:40:32+00:00
- Post Title: Re: Nier Automata

Is it possible to extract each individual character's voice lines?
## Post #24
- Username: xrb936
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 23, 2017 1:48 pm
- Post datetime: 2017-03-24T03:16:07+00:00
- Post Title: Re: Nier Automata

> Reply from marcussacana
>
> Okay, i extracted the data009.cpk, extracted the "subtitle\subtitle1270_us.dat" (contains new game cutscene subtitle)
After this, i translated and recreated the .dat without problem... and i patch the .cpk... but
WTF the text don't change.... i confirm if the old text contains in the new data009.cpk but yes, not found... i have sure the tools works and the file has been edited, but the game don't change anything... probabbly have the file in another packget/folder, anyone found the correct file?
After I unpack the subtitle1270_us.dat file, I just got a .smd file. Do you have any idea how to edit it?
## Post #25
- Username: Eiwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Dec 21, 2011 10:06 am
- Post datetime: 2017-03-24T08:39:25+00:00
- Post Title: Re: Nier Automata

> Reply from Voye
>
> Is it possible to extract each individual character's voice lines?

Yes, read above for the tool. And use [https://mega.nz/#!qNIXyYhZ!Swj9p_NKNcqh ... PL-2G8Jbh4](https://mega.nz/#!qNIXyYhZ!Swj9p_NKNcqhxoRHjz_gzZNJFn6qAiFImPL-2G8Jbh4) which has a .bat file in it, found it over on Steam's Nier forums.
## Post #26
- Username: Voye
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 24, 2017 8:09 am
- Post datetime: 2017-03-24T14:11:46+00:00
- Post Title: Re: Nier Automata

> Reply from Eiwo
>
> Yes, read above for the tool. And use https://mega.nz/#!qNIXyYhZ!Swj9p_NKNcqh ... PL-2G8Jbh4 which has a .bat file in it, found it over on Steam's Nier forums.

Sorry, I'm new to this. Do I extract Audio.zip anywhere? Nothing happens when I run the files
## Post #27
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-03-24T21:53:14+00:00
- Post Title: Re: Nier Automata

> Reply from xrb936
>
> marcussacana wrote:Okay, i extracted the data009.cpk, extracted the "subtitle\subtitle1270_us.dat" (contains new game cutscene subtitle)
After this, i translated and recreated the .dat without problem... and i patch the .cpk... but
WTF the text don't change.... i confirm if the old text contains in the new data009.cpk but yes, not found... i have sure the tools works and the file has been edited, but the game don't change anything... probabbly have the file in another packget/folder, anyone found the correct file?
After I unpack the subtitle1270_us.dat file, I just got a .smd file. Do you have any idea how to edit it?

i write a tool to edit this file: [https://github.com/marcussacana/AutomataTranslator](https://github.com/marcussacana/AutomataTranslator)
but the .smd it's the text only of the cutscene subtitle... i don't have a method to translate the .bin (mruby) script
## Post #28
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-03-24T21:58:45+00:00
- Post Title: Re: Nier Automata

> Reply from makcar
>
> xrb936 wrote:Hi everyone,

I am trying to make a localization for my language, do you guys know where all texts stored? I don't really know which file is correct.

Thank you!
https://yadi.sk/d/3MsyUHRK3G79GN

Perfect, but and how we can insert the translation?
## Post #29
- Username: Eiwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Dec 21, 2011 10:06 am
- Post datetime: 2017-03-27T04:57:02+00:00
- Post Title: Re: Nier Automata

> Reply from Voye
>
> Eiwo wrote:Yes, read above for the tool. And use https://mega.nz/#!qNIXyYhZ!Swj9p_NKNcqh ... PL-2G8Jbh4 which has a .bat file in it, found it over on Steam's Nier forums.

Sorry, I'm new to this. Do I extract Audio.zip anywhere? Nothing happens when I run the files
Drag and drop onto the bat file. Or was it double click on it? I forget
## Post #30
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2017-03-28T07:37:33+00:00
- Post Title: Re: Nier Automata

I was digging into the animation files and managed to extract 1 frame animations. I mapped out MOT files to the best of my limited ability:

```
	SHORT	BoneID;
	UBYTE	Channel; 	// "0-POSX 1-POSY 2-POSZ 3-ROTX 4-ROTY 5-ROTZ
	ULONG	FrameThing; 	// "When this is filled Float changes and 8 bytes are added to the bottom of the file"
	UBYTE	Blank0;
	float	Float;
} BoneArray;

struct MOT
{
	char		fourCC[4]; 	// "MOT"
	ULONG		UNK0;
	SHORT		Blank;
	SHORT		UNK1;
	ULONG		Offset1; 	//"Bone List offset"
	ULONG		ListCount;
	ULONG		UNK1;
	char		Name[20];
	BoneArray	BoneStuff[ListCount];

};
```


As long as the animation is 1 frame long, its easy enough to understand. But longer animations have some nonsense at the bottom of the file that I don't understand.
## Post #31
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2017-03-28T20:01:33+00:00
- Post Title: Re: Nier Automata

> Reply from Simguy
>
> 
Code: Select all	ULONG		Offset1; 	//"Bone List offset"
	ULONG		ListCount;
Just a note about the file formats in general to anyone writing any readers or max scripts but these "list offset, list count" pairs are littered everywhere among the file formats so I've interpreted them as structures:

```
struct TableReference
{
   typedef EntryType ElementType; // For reading functions
   std::uint32_t Offset;
   std::uint32_t Count;
};

```

in C++ using templates to store the type of the table which allows for some very adaptive code to be written even when tables get very nested(this is probably what Platinum's source code is doing as there has to be some statically available data for it to determine how to read these structures such as the size of each element). If any of you out there are making readers I recommend something something like this so you aren't writing deeply nested table-reference-resolvers when things are actually pretty "flat". You can write one "ReadTable" function that could recursively read in any nested tables and return a vector of the table's ElementType. The offsets seem file-relative but should the file be loaded entirely into memory then you can use these same offsets for pointer arithmetic to avoid having to seek and read all around a file.
With this an entire "Table reference" of 32-bit integers can be declared as

```
TableReference<std::uint32_t> SomeTable;
```


I'll release my model-reader code as info gets mapped out and will probably write a converter using the fbxsdk.
## Post #32
- Username: c0d3s1ing3r
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 31, 2017 4:12 am
- Post datetime: 2017-03-30T20:20:55+00:00
- Post Title: Re: Nier Automata

Hello everyone!

I was the one who amassed that Audio.zip file. It works by dragging the bnk files onto the bnkextr.exe . That will turn it into a collection of wems which you can then convert to ogg by running wem2ogg.bat. Windows media player can run those files (but I prefer Winamp).

delwems just deletes the .wem files if you have no use for them anymore.

However a much better solution is to just use the sound extractor someone else made (it's what I used) since that opens the .wsp files no problem.

In addition, anything that I manage to fully extract I post to the [Modding and Mining Group](http://steamcommunity.com/groups/nierMnM) that I setup on Steam. I'd love it if you guys joined and posted there too.

It's worth mentioning that one of the posts there has a full download to the output of nier-sound-extractor.
## Post #33
- Username: SkacikPL
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Oct 28, 2014 2:51 pm
- Post datetime: 2017-04-04T17:33:16+00:00
- Post Title: Re: Nier Automata

Is the interest in reverse engineering this game already dead?
Seems to be a shame seeing that's it's one of best action JRPGs of late and it could really use some texture mods.
## Post #34
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2017-04-04T18:11:09+00:00
- Post Title: Re: Nier Automata

It's not dead I don't think but a lot of people have been keeping to themselves for whatever reason. It seems like a lot of people just wanted to get 2B's model to shove into SFM or GMOD or whatever. There are people that are legitimately interested in the mruby vm to try and get a translation made for their region but without a decompiler or dat+cpk repacker that's looking to be a pretty mute effort.
## Post #35
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-04-05T00:58:09+00:00
- Post Title: Re: Nier Automata

> Reply from DEElekgolo
>
> It's not dead I don't think but a lot of people have been keeping to themselves for whatever reason. It seems like a lot of people just wanted to get 2B's model to shove into SFM or GMOD or whatever. There are people that are legitimately interested in the mruby vm to try and get a translation made for their region but without a decompiler or dat+cpk repacker that's looking to be a pretty mute effort.
in my case i just need translate this shit to ptbr, but the tool created to a rus project isn't published... i wrote a tool to edit the cutscene subtitle and published the source... but looks the rus devs as wrote your tools to yourself... i hope publish after translate (carefull with stolen credits maybe?), anyway with mruby my position is just wait and see if anyone publish a tool


-eddit
and in the first page i publish my "stuff" of the .cpk and .dat, the tools are stable and i fully extracted and repacked the .cpk/.dat files, and obvious, with modification to confirm, i translate all cutscenes to my language using my tool
## Post #36
- Username: c0d3s1ing3r
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 31, 2017 4:12 am
- Post datetime: 2017-04-05T15:36:51+00:00
- Post Title: Re: Nier Automata

> Reply from SkacikPL
>
> Is the interest in reverse engineering this game already dead?
Seems to be a shame seeing that's it's one of best action JRPGs of late and it could really use some texture mods.

Not dead, just plenty of the people who would be doing this are busy (myself with college).

I expect that at summer the game will start accruing more interest again.
## Post #37
- Username: marcussacana
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2017-04-07T21:09:34+00:00
- Post Title: Re: Nier Automata

> Reply from marcussacana
>
> DEElekgolo wrote:It's not dead I don't think but a lot of people have been keeping to themselves for whatever reason. It seems like a lot of people just wanted to get 2B's model to shove into SFM or GMOD or whatever. There are people that are legitimately interested in the mruby vm to try and get a translation made for their region but without a decompiler or dat+cpk repacker that's looking to be a pretty mute effort.
in my case i just need translate this shit to ptbr, but the tool created to a rus project isn't published... i wrote a tool to edit the cutscene subtitle and published the source... but looks the rus devs as wrote your tools to yourself... i hope publish after translate (carefull with stolen credits maybe?), anyway with mruby my position is just wait and see if anyone publish a tool


-eddit
and in the first page i publish my "stuff" of the .cpk and .dat, the tools are stable and i fully extracted and repacked the .cpk/.dat files, and obvious, with modification to confirm, i translate all cutscenes to my language using my tool

So there is not public tool for localization yet ? Anyone ? Damn i publish so many tools for most complicated games someone could help out right ?  I dont want to go and do research again if someone allready did it, that is nonsence...
## Post #38
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2017-04-07T21:31:29+00:00
- Post Title: Re: Nier Automata

> Reply from michalss
>
> I dont want to go and do research again if someone allready did it, that is nonsence...Not if said research disappears for about 10+ years.
## Post #39
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-04-07T22:52:17+00:00
- Post Title: Re: Nier Automata

> Reply from michalss
>
> 
So there is not public tool for localization yet ? Anyone ? Damn i publish so many tools for most complicated games someone could help out right ?  I dont want to go and do research again if someone allready did it, that is nonsence...
Yes... If you have a free time to this, I would be grateful

Screenshot of the russian project:
## Post #40
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-04-08T19:09:10+00:00
- Post Title: Re: Nier Automata

> Reply from michalss
>
> well thats the problem i dont have a time..

no problem... i wait the russian project finish... i hope after finish he publish the tool, otherwise i can try see the offsets changes comparing the original and translated script, and maybe i can write a tool
## Post #41
- Username: SkacikPL
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Oct 28, 2014 2:51 pm
- Post datetime: 2017-04-08T19:10:51+00:00
- Post Title: Re: Nier Automata

> Reply from marcussacana
>
> michalss wrote:well thats the problem i dont have a time..

no problem... i wait the russian project finish... i hope after finish he publish the tool, otherwise i can try see the offsets changes comparing the original and translated script, and maybe i can write a tool
Have you tried simply contacting the author?
## Post #42
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2017-04-08T19:52:37+00:00
- Post Title: Re: Nier Automata

> Reply from marcussacana
>
> i wait the russian project finish... i hope after finish he publish the tool
Ok, that's a bargain! +src?
## Post #43
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-04-09T02:30:10+00:00
- Post Title: Re: Nier Automata

> Reply from makcar
>
> marcussacana wrote:i wait the russian project finish... i hope after finish he publish the tool
Ok, that's a bargain! +src?
I'd be grateful, but whatever, as long as I can translate it's perfect
## Post #44
- Username: SkacikPL
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Oct 28, 2014 2:51 pm
- Post datetime: 2017-04-09T16:34:39+00:00
- Post Title: Re: Nier Automata

> Reply from marcussacana
>
> makcar wrote:marcussacana wrote:i wait the russian project finish... i hope after finish he publish the tool
Ok, that's a bargain! +src?
I'd be grateful, but whatever, as long as I can translate it's perfect
Do you have any contact with the author or some more information?
He might share if someone asks politely?
## Post #45
- Username: Slokky
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 10, 2017 11:19 pm
- Post datetime: 2017-04-10T15:27:55+00:00
- Post Title: Re: Nier Automata

> Reply from SkacikPL
>
> 
Do you have any contact with the author or some more information?
He might share if someone asks politely?
makcar
is autor of the russian mod XD







PS guys is there some config file in the  game archives?  We need fix the draw distance and the shadow resolution.
## Post #46
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2017-04-10T15:48:35+00:00
- Post Title: Re: Nier Automata

> Reply from Slokky
>
> SkacikPL wrote:
Do you have any contact with the author or some more information?
He might share if someone asks politely?
makcar
is autor of the russian mod XD



PS guys is there some config file in the  game archives?  We need fix the draw distance and the shadow resolution.

Do you have any way how to contact him ? On PM pls
## Post #47
- Username: SkacikPL
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Oct 28, 2014 2:51 pm
- Post datetime: 2017-04-10T19:47:03+00:00
- Post Title: Re: Nier Automata

> Reply from Slokky
>
> 
PS guys is there some config file in the  game archives?  We need fix the draw distance and the shadow resolution.
Doesn't seem to be the case, i also wouldn't bet on the engine to scale well. I mean all settings are pretty much rendering related, like AF, resolution or MSAA. Then there's post processing setting and that's that, nothing that would actually influence the engine itself like mesh/texture quality.

Since it's a primarily console game i assume that 80% of stuff is hardcoded and that's that.
## Post #48
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-04-10T20:37:17+00:00
- Post Title: Re: Nier Automata

> Reply from michalss
>
> 
Do you have any way how to contact him ? On PM pls

he says "Ok, that's a bargain! +src?" looks he can help us
## Post #49
- Username: delguoqing
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 12, 2014 9:55 am
- Post datetime: 2017-04-21T08:00:07+00:00
- Post Title: Re: Nier Automata

hi, every one.
I have pretty much figured out the wmb format and made a Blender addon. 
The importer will import meshes with the official rig. If dds files is put in the same folder, it will try to give a default material with textures assigned.

Usage:
1.run src/wmb_parser.py to generate an itermediate file for model. (*.gtb)
2.run src/splitdds.py to get the textures related to that model, put textures in the same directory with gtb file. Materials match textures by some hash or stringid, which is stored in a ".wta" file. ".wtp" file stores the actual texture data. run this script with wta and wtp files specified, and it will generate the textures needed.
3.if using blender, then put the "gtb_importer" folder into blender's addon folder. Enable that addon and you can import gtb files into blender. if you have dds files with gtb files in the same folder.then Blender will try to apply a default material for you, with textures assigned. However, to get the same visuals like the game, you have to setup your own pbr material.
4.if not using blender, then edit "src/wmb_parser.py", set DUMP_OBJ to True, and you'll get obj files instead.

known issues:
custom vertex normal is quite right.
joints and weights for some models are not correct.

PS:
gtb file is just a zlib compressed json file with fourcc "GTB\x00"
I use this custom format so that I don't have to write Blender importer for every single game.
Also, one can write importers for other DCC tools such as MAX and maya, without knowing details of wmb file.
So feel free to make importer for your favourite DCC tool.
check "src/wmb_parser.py" export_gtb for detail.
[nier_importer.7z](https://xentaxbackup.github.io/file/12802_nier_importer.7z)
## Post #50
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-04-21T14:34:31+00:00
- Post Title: Re: Nier Automata

Thank you very much! 
Any word on how to get the wmb parser to work? Does it require a specific Python version?
## Post #51
- Username: delguoqing
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 12, 2014 9:55 am
- Post datetime: 2017-04-21T15:13:29+00:00
- Post Title: Re: Nier Automata

> Reply from o0Crofty0o
>
> Thank you very much! 
Any word on how to get the wmb parser to work? Does it require a specific Python version?

I'm using python 2.7.8, and most likely it will work with 2.7.x.

Make sure you have python installed, then run the script with the wmb file path as argument.
for example:
python wmb_parser.py D:\data006\pl\pl000_dtt\pl000.wmb

A gtb file should be generated in the same directory as the wmb file. Then you can use Blender addon to import it.

Here's what it should look like in Blender.



9S.png (154.17 KiB) Viewed 1088 times
## Post #52
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-04-21T15:33:30+00:00
- Post Title: Re: Nier Automata

Thanks, that worked now =)
## Post #53
- Username: ss201314
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 25, 2017 7:15 am
- Post datetime: 2017-04-25T00:04:01+00:00
- Post Title: Re: Nier Automata

I am a novice
Sorry for my bad english
I try to extract the a2 model from pso2
But stopped at a step
"DeCompressed.bin" is a puzzle
I do not know how to extract
any ideas?

[1.JPG](https://xentaxbackup.github.io/file/12817_1.JPG)
## Post #54
- Username: Pokkentag
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Mar 20, 2017 6:45 pm
- Post datetime: 2017-04-25T02:11:37+00:00
- Post Title: Re: Nier Automata

Thank you delguoqing for providing those scripts.  However, I am having trouble installing the gtb_importer to blender.  I followed your instructions but blender seems to be having trouble recognizing the addon.  Any help would be appreciated.  Also, not sure if I was doing this correctly but when i tried to use the wmb_parser.py, it had an error.  It stated "ImportError: No module named numpy"  Any idea what I did wrong?  I am a newbie so I need all the help I can get.  Thanks to all contributors of this thread.
## Post #55
- Username: yarrmateys
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 20, 2012 9:41 am
- Post datetime: 2017-04-25T07:57:17+00:00
- Post Title: Re: Nier Automata

you need to install that module.

[https://sourceforge.net/projects/numpy/ ... mPy/1.9.2/](https://sourceforge.net/projects/numpy/files/NumPy/1.9.2/)

this should be enough (was for me), and it's easy to install since it's just an exe, while the newest one is in some convoluted format. it is for me. get the 2.7 version. make sure it's the same bit version as your python.
## Post #56
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2017-04-25T08:06:49+00:00
- Post Title: Re: Nier Automata

Here is a massive,massive, automated dump I made of a bunch of "StringBanks" I found at run-time complete with their string IDs and some little markups for if the stringbanks are empty

[https://paste.ee/p/zt17P](https://paste.ee/p/zt17P)

Naturally, there are major, major spoilers in here.

String checksums(besides item IDs) are just regular CRC32's of the script-name after making all characters lowercase.

eg: "PAUSE_PICTUREBOOK_00" is a string's script name that is looked up in the string bank.

first it converts the string to the lowercase "pause_picturebook_00" and takes a crc32 of it(0x577D2592) using polynomial 0xEDB88320.
It then looks up "577D2592" within the appropriate string bank and does a binary search until it finds the associated string for the currently loaded language. 

In this case it matches up with the string "View "<BOOK_NAME>"?" 
At run-time "<BOOK_NAME>" is replaced with the appropriate value using sub_1406FFD60.

I'll make a more nicely formatted and categorized list later but feel free to use the dump meanwhile. Will probably wait for the DLC+Update next week before I do anything new.
If cpks/dats ever get re-packed then translating the game might end up being very easy if this is how localization works.
## Post #57
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-04-25T14:18:43+00:00
- Post Title: Re: Nier Automata

> Reply from DEElekgolo
>
> Here is a massive,massive, automated dump I made of a bunch of "StringBanks" I found at run-time complete with their string IDs and some little markups for if the stringbanks are empty

https://paste.ee/p/zt17P

Naturally, there are major, major spoilers in here.

String checksums(besides item IDs) are just regular CRC32's of the script-name after making all characters lowercase.

eg: "PAUSE_PICTUREBOOK_00" is a string's script name that is looked up in the string bank.

first it converts the string to the lowercase "pause_picturebook_00" and takes a crc32 of it(0x577D2592) using polynomial 0xEDB88320.
It then looks up "577D2592" within the appropriate string bank and does a binary search until it finds the associated string for the currently loaded language. 

In this case it matches up with the string "View "<BOOK_NAME>"?" 
At run-time "<BOOK_NAME>" is replaced with the appropriate value using sub_1406FFD60.

I'll make a more nicely formatted and categorized list later but feel free to use the dump meanwhile. Will probably wait for the DLC+Update next week before I do anything new.
If cpks/dats ever get re-packed then translating the game might end up being very easy if this is how localization works.
man in the first page i put a .rar with a .dat/.cpk repack tool. it works, i test here.
We just need the tool to translate the mruby scripts now...

Open the .bat in my rar and update the CD command
## Post #58
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2017-04-25T15:23:47+00:00
- Post Title: Re: Nier Automata

> Reply from marcussacana
>
> 
man in the first page i put a .rar with a .dat/.cpk repack tool. it works, i test here.
We just need the tool to translate the mruby scripts now...

Open the .bat in my rar and update the CD command
There is no current .cpk repacker for the more current format I didn't think(that cpk repacker is from like 2008, the dat tool is for metal gear rising). Have yet to see anyone publish info on the string-tables and more people keeping to themselves.


Anyways the mruby scripts in particular use the same crc32s and string-identifiers as before to identify pretty much all the bindings among other things. Some lose structures from my notes. I think you're better off finding the (several) string tables within the cpk/dat files and you can pretty much translate the entire game by repacking that. There are several of them for items and skills and dialog and one named "core". They get put into a sorted array based on their crc32 as well and is how they are mostly identified in the mruby binaries.

Some dumps from my notes.

```
{
	std::uint32_t CommandCRC;

// function offsets, argument data, etc
	std::uint32_t Unknown4;
	std::uint64_t UnknownOffset8;
	std::uint64_t UnknownOffset10;
	std::uint64_t UnknownOffset18;
	std::uint64_t UnknownOffset20;
};

struct StringBankRef
{
	void* Unknown0;
	std::uint64_t Unknown8;
	std::uint64_t Unknown10;
	char16_t* RawTextStream;
	std::uint64_t Unknown20;
	std::uint64_t Unknown28;
	std::uint64_t Unknown30;
	std::uint64_t Unknown38;
	std::uint64_t Unknown40;
	void* TableEntryOffset;
};

struct StringGroup
{
	void* StringTablePtr;
	std::uint32_t Unknown8;
	std::uint32_t UnknownC;
	std::uint32_t StringCount;
};

struct StringEntry
{
	std::uint64_t StringChecksum; // CRC32
	char16_t* StringName;
	std::uint64_t RawTextStreamOffset; // offset within StringBankRef::RawTextStream
	std::uint64_t StringSize;
	char16_t* ScriptName;
}
```


Some of the memory pools it allocates. Note that in about a week much of these runtime offsets are going to be useless.

```
struct HeapReference
{
	HeapReference* Previous;
	void* HeapLocation
	HeapReference* Next;
}

Name|Offset|Size|Group
-|-|-|-
"GRAPHIC WORK" | 0x1418DC668 | 0x3200000 | 0x1418DC578 (System)
"GLOBAL" | 0x1418DC698 | 0x5500000 | 0x1418DC578 (System)
"SOUND" | 0x1418DC6F8 | 0x1700000 | 0x1418DC578 (System)
"EFFECT_GLOBAL" | 0x1418DC728 | 0xC00000 | 0x1418DC578 (System)
"UI" | 0x1418DC788 | 0xC00000 | 0x1418DC578 (System)
"UIFont" | 0x1418DC7B8 | 0x100000 | 0x1418DC578 (System)
"MODEL RESOURCE" | 0x1418DC7E8 | 0x200000 | 0x1418DC578 (System)
"ONLINE" | 0x1418DC818 | 0x100000 | 0x1418DC578 (System)
"GRAPHIC BUFFER" | 0x1418DC848 | 0xFF00000 | 0x1418DC5A8 (Buffer)
"EFF+UI BUFFER" | 0x1418DC8A8 | 0x2980000 | 0x1418DC5A8 (Buffer)
"GRAPHIC GPURW BUFFER" | 0x1418DC878 | 0xCD00000 | 0x1418DC5D8 (Unknown)
"CORE FILE" | 0x1418DC8D8 | 0x6400000 | 0x1418DC608 (File)
"PL FILE" | 0x1418DC908 | 0x3E40000 | 0x1418DC608 (File)
"CELE FILE" | 0x1418DC938 | 0x40000 | 0x1418DC608 (File)
"EM+BG FILE" | 0x1418DC968 | 0x4400000 | 0x1418DC608 (File)
"RESIDENTS FILE" | 0x1418DCA28 | 0x1500000 | 0x1418DC608 (File)
"HIGH MAP FILE" | 0x1418DC998 | 0x9A00000 | 0x1418DC608 (File)
"LOW MAP FILE" | 0x1418DC9C8 | 0x2900000 | 0x1418DC608 (File)
"MAP SHARE FILE" | 0x1418DC9F8 | 0x80000 | 0x1418DC608 (File)
"UI FILE" | 0x1418DCA58 | 0x800000 | 0x1418DC608 (File)
"UIFont FILE" | 0x1418DCA88 | 0x500000 | 0x1418DC608 (File)
"UI MINIMAP FILE" | 0x1418DCAB8 | 0x40000 | 0x1418DC608 (File)
"SHADER FILE" | 0x1418DCAE8 | 0x480000 | 0x1418DC608 (File)
"EFF SHADER FILE" | 0x1418DCB18 | 0x400000 | 0x1418DC608 (File)
"HACKING FILE" | 0x1418DCB48 | 0x800000 | 0x1418DC608 (File)
"BOOK FILE" | 0x1418DCB78 | 0x180000 | 0x1418DC608 (File)
"MOVIE FILE" | 0x1418DCBA8 | 0x3FC0000 | 0x1418DC608 (File)
"GRAPHIC VRAM" | 0x1418DCBD8 | 0x20000 | 0x1418DC638 (Vram)
"CORE VRAM" | 0x1418DCC08 | 0xA00000 | 0x1418DC638 (Vram)
"PL VRAM" | 0x1418DCC38 | 0x7800000 | 0x1418DC638 (Vram)
"CELE VRAM" | 0x1418DCC68 | 0x1600000 | 0x1418DC638 (Vram)
"EM+BG VRAM" | 0x1418DCC98 | 0x37880000 | 0x1418DC638 (Vram)
"RESIDENTS VRAM" | 0x1418DCD58 | 0x8800000 | 0x1418DC638 (Vram)
"HIGH MAP VRAM" | 0x1418DCCC8 | 0x2BC00000 | 0x1418DC638 (Vram)
"LOW MAP VRAM" | 0x1418DCCF8 | 0xC700000 | 0x1418DC638 (Vram)
"MAP SHARE VRAM" | 0x1418DCD28 | 0xB900000 | 0x1418DC638 (Vram)
"EFFECT VRAM" | 0x1418DCD88 | 0xB400000 | 0x1418DC638 (Vram)
"UI VRAM" | 0x1418DCDB8 | 0x1800000 | 0x1418DC638 (Vram)
"UIFont VRAM" | 0x1418DCDE8 | 0x12000000 | 0x1418DC638 (Vram)
"UI MINIMAP VRAM" | 0x1418DCE18 | 0x380000 | 0x1418DC638 (Vram)
"HACKING VRAM" | 0x1418DCE48 | 0x200000 | 0x1418DC638 (Vram)
"BOOK VRAM" | 0x1418DCE78 | 0x3080000 | 0x1418DC638 (Vram)
"MOVIE VRAM" | 0x1418DCEA8 | 0x1E00000 | 0x1418DC638 (Vram)

```


Also those russians that are translating the game are probably going to be somewhat at ground-zero again once the dlc+update comes out next week and any research-breaking changes happen.
## Post #59
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-04-25T19:22:50+00:00
- Post Title: Re: Nier Automata

Hmm, i repack without problem here to edit the cutscene subtitle
## Post #60
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-04-25T20:01:54+00:00
- Post Title: Re: Nier Automata

about the suppose of a method to edit, can talk more?
## Post #61
- Username: atvaark
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Aug 28, 2015 10:19 pm
- Post datetime: 2017-04-25T21:52:52+00:00
- Post Title: Re: Nier Automata

The TMD format is also pretty straightforward. It's used for UI key values e.g.
"CORE_QUEST_EMP_TXT_ITEM" ->  "<ITEM_NAME> x <ITEM_NUM>"

```
  int count;
  Entry entries[count];
} TMDFile;

typedef struct {
  int keySize;
  wchar_t key[keySize];
  int valueSize;
  wchar_t value[valueSize];
} Entry

```
## Post #62
- Username: ss201314
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 25, 2017 7:15 am
- Post datetime: 2017-04-26T14:45:20+00:00
- Post Title: Re: Nier Automata

Finally succeeded!!

Although it is pso2 model......
## Post #63
- Username: SkacikPL
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Oct 28, 2014 2:51 pm
- Post datetime: 2017-04-27T08:23:54+00:00
- Post Title: Re: Nier Automata

> Reply from marcussacana
>
> about the suppose of a method to edit, can talk more?
Well, sharing the method would be much appreciated.
## Post #64
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-04-27T14:24:45+00:00
- Post Title: Re: Nier Automata

> Reply from SkacikPL
>
> 
Well, sharing the method would be much appreciated.
do not count on me. I dont know too
## Post #65
- Username: painpi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 04, 2017 8:31 pm
- Post datetime: 2017-05-04T23:15:30+00:00
- Post Title: Re: Nier Automata

> Reply from delguoqing
>
> o0Crofty0o wrote:Thank you very much! 
Any word on how to get the wmb parser to work? Does it require a specific Python version?

I'm using python 2.7.8, and most likely it will work with 2.7.x.

Make sure you have python installed, then run the script with the wmb file path as argument.
for example:
python wmb_parser.py D:\data006\pl\pl000_dtt\pl000.wmb

A gtb file should be generated in the same directory as the wmb file. Then you can use Blender addon to import it.

Here's what it should look like in Blender.
9S.png

Hello, it`s my first time to use English communicate with others, sorry for my poor English
could you please show me an example of using the splitdds.py? i spent a lot of time but have no progress.now i can import the gtb file but no textures for my models.
## Post #66
- Username: delguoqing
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 12, 2014 9:55 am
- Post datetime: 2017-05-05T01:25:11+00:00
- Post Title: Re: Nier Automata

> Reply from painpi
>
> delguoqing wrote:o0Crofty0o wrote:Thank you very much! 
Any word on how to get the wmb parser to work? Does it require a specific Python version?

I'm using python 2.7.8, and most likely it will work with 2.7.x.

Make sure you have python installed, then run the script with the wmb file path as argument.
for example:
python wmb_parser.py D:\data006\pl\pl000_dtt\pl000.wmb

A gtb file should be generated in the same directory as the wmb file. Then you can use Blender addon to import it.

Here's what it should look like in Blender.
9S.png

Hello, it`s my first time to use English communicate with others, sorry for my poor English
could you please show me an example of using the splitdds.py? i spent a lot of time but have no progress.now i can import the gtb file but no textures for my models.

python splitdds.py --wtp your_wtp_file_path --wta your_wta_file_path

There's an easier way to save you a lot of time, for example, if you have all dtt and dat files unpacked in data006, then the command below will search wta and wtp pairs, and extract all textures.
python build_texture.py data006 your_output_path_here

make sure all these textures and gtb files are in the same folder, then you can get your model textured when imported into Blender.
## Post #67
- Username: painpi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 04, 2017 8:31 pm
- Post datetime: 2017-05-05T04:53:00+00:00
- Post Title: Re: Nier Automata

> Reply from delguoqing
>
> 

python splitdds.py --wtp your_wtp_file_path --wta your_wta_file_path

There's an easier way to save you a lot of time, for example, if you have all dtt and dat files unpacked in data006, then the command below will search wta and wtp pairs, and extract all textures.
python build_texture.py data006 your_output_path_here

make sure all these textures and gtb files are in the same folder, then you can get your model textured when imported into Blender.
thanks very much！！！I can now use this time to do more things,such as animating my favorite characters.
## Post #68
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-05-05T05:50:19+00:00
- Post Title: Re: Nier Automata

...some time after...
"2 new reply in the Nier Automata"
... "Maybe, now!"
... nothing...

Anyway, any news about the mruby?
## Post #69
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2017-05-06T20:52:30+00:00
- Post Title: Re: Nier Automata

Does anyone know where menu text and all local string are pls ? This is not in mruby files, so it must be elsewhere..
## Post #70
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-05-07T03:32:50+00:00
- Post Title: Re: Nier Automata

> Reply from michalss
>
> Does anyone know where menu text and all local string are pls ? This is not in mruby files, so it must be elsewhere..

you look this files?


and why need you the menu strings if we can't edit the story scripts?
## Post #71
- Username: Pokkentag
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Mar 20, 2017 6:45 pm
- Post datetime: 2017-05-08T10:23:42+00:00
- Post Title: Re: Nier Automata

Hi, I need help.  I cannot get the gtb_importer addon to work for blender.  Can someone tell me which version of blender they are using?
## Post #72
- Username: Pokkentag
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Mar 20, 2017 6:45 pm
- Post datetime: 2017-05-08T20:27:45+00:00
- Post Title: Re: Nier Automata

nevermind, i got it to work.  thanks delguoqing again for this awesome script.
## Post #73
- Username: SkacikPL
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Oct 28, 2014 2:51 pm
- Post datetime: 2017-05-09T12:47:56+00:00
- Post Title: Re: Nier Automata

Speaking off-tangent but has anyone tried to do in-game model replacement by simply switching files within the game?

Also the 10th pod skin - Amazarashi head seems to be intact as item/script in PC version but model is removed, anyone attempted borrowing it from console version?
## Post #74
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2017-05-11T00:04:29+00:00
- Post Title: Re: Nier Automata

> Reply from Pokkentag
>
> nevermind, i got it to work.  thanks delguoqing again for this awesome script.

Hi! how are you doing? I noticed your message on the forum. I faced the same problem as you. Can't install the gtb_importer. How did you manage to fix it?
## Post #75
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2017-05-11T04:58:04+00:00
- Post Title: Re: Nier Automata

> Reply from marcussacana
>
> michalss wrote:Does anyone know where menu text and all local string are pls ? This is not in mruby files, so it must be elsewhere..

you look this files?


and why need you the menu strings if we can't edit the story scripts?

We it is not a problem anymore, but problem  is that i cannot find the main menu string so it looks like it is textures. Try to search for example for "New Game".
## Post #76
- Username: nenkitsune
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 11, 2017 7:23 pm
- Post datetime: 2017-05-11T11:24:44+00:00
- Post Title: Re: Nier Automata

Ok, I've hit my limit. I'm trying to mess around with the BGM files, I can extract them, convert them to OGG, convert them back to WEM, but how in the hell do I repack them back into a WSP?
## Post #77
- Username: Pokkentag
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Mar 20, 2017 6:45 pm
- Post datetime: 2017-05-12T02:59:17+00:00
- Post Title: Re: Nier Automata

> Reply from lyutor1945
>
> Pokkentag wrote:nevermind, i got it to work.  thanks delguoqing again for this awesome script.

Hi! how are you doing? I noticed your message on the forum. I faced the same problem as you. Can't install the gtb_importer. How did you manage to fix it?

I dont know exactly how.  What I did was I download the latest version of blender 2.78 and it worked.  Hopefully it works the same for you.
## Post #78
- Username: atvaark
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Aug 28, 2015 10:19 pm
- Post datetime: 2017-05-12T06:21:37+00:00
- Post Title: Re: Nier Automata

> Reply from nenkitsune
>
> Ok, I've hit my limit. I'm trying to mess around with the BGM files, I can extract them, convert them to OGG, convert them back to WEM, but how in the hell do I repack them back into a WSP?
WSP is just a concatenation of the WEM files with 255 bytes alignment. You'll have to figure out where the offsets to each WEM is stored or you can't use files sizes bigger than the original WEMs.
## Post #79
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-05-19T04:11:53+00:00
- Post Title: Re: Nier Automata

Hi, i write my tool to translate the .bin files: [https://github.com/marcussacana/AutomataTranslator](https://github.com/marcussacana/AutomataTranslator)
Works but he need delete some language of the game to overwrite...

And i found this tool to translate too... (unstable): [https://github.com/micktu/att](https://github.com/micktu/att)
## Post #80
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2017-05-19T20:56:31+00:00
- Post Title: Re: Nier Automata

> Reply from marcussacana
>
> Hi, i write my tool to translate the .bin files: https://github.com/marcussacana/AutomataTranslator
Works but he need delete some language of the game to overwrite...

And i found this tool to translate too... (unstable): https://github.com/micktu/att

Well in this game is 3 different format for texts. Also special format for Menu and locals, very messy. Did you also made tools for that ?
## Post #81
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-05-20T20:54:54+00:00
- Post Title: Re: Nier Automata

My tools are only to .smd and .bin

the .mcd have this struct to help: [http://zenhax.com/viewtopic.php?t=1502& ... witterfeed](http://zenhax.com/viewtopic.php?t=1502&p=8181#p8181&utm_medium=twitter&utm_source=twitterfeed)
the .mcd is the menu text i think, he do not have encryption but the text format is a shit...
He contains entries of the position of a char in the font (s0001.dat>s0001.mcd => s0001.dtt) and the "string" in the .mdc is a sequence of index of the char entry... soo, is a little shit edit this...

the .dtt is like the .dat, contains just a .dds

The .dat and .pck i sent a mediafire url in the frist page of this topic.

have the .tmd, i do not created a tool to this format, but i think is just something like this

```
int32 StrCount;
TMDEntry[] Content = new TMDEntry[StrCount];
}
struct TMDEntry{
int32 len;
byte[] Buffer = new byte[len*2];
}

```


anyway to the tmd i can wrote a code after...

CPK with text is: data002, data009, data012, data013, data100

i think is this:
SMD => Cutscene Subtitle
Bin => In Game Text
MCD => Menu/UI Text
DTT => A part of the .mcd, the font/texture.
TMD => I think is itens description, but looks have a general content.

--edit
Now my tool support the TMD.
## Post #82
- Username: Anony
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 20, 2017 12:10 pm
- Post datetime: 2017-05-21T14:03:39+00:00
- Post Title: Re: Nier Automata

> Reply from delguoqing
>
> o0Crofty0o wrote:Thank you very much! 
Any word on how to get the wmb parser to work? Does it require a specific Python version?

I'm using python 2.7.8, and most likely it will work with 2.7.x.

Make sure you have python installed, then run the script with the wmb file path as argument.
for example:
python wmb_parser.py D:\data006\pl\pl000_dtt\pl000.wmb

A gtb file should be generated in the same directory as the wmb file. Then you can use Blender addon to import it.

Here's what it should look like in Blender.
9S.png

When I try to run the script with the wmb file path as argument I get SyntaxError: invalid syntax
## Post #83
- Username: delguoqing
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 12, 2014 9:55 am
- Post datetime: 2017-05-21T15:14:45+00:00
- Post Title: Re: Nier Automata

> Reply from Anony
>
> delguoqing wrote:o0Crofty0o wrote:Thank you very much! 
Any word on how to get the wmb parser to work? Does it require a specific Python version?

I'm using python 2.7.8, and most likely it will work with 2.7.x.

Make sure you have python installed, then run the script with the wmb file path as argument.
for example:
python wmb_parser.py D:\data006\pl\pl000_dtt\pl000.wmb

A gtb file should be generated in the same directory as the wmb file. Then you can use Blender addon to import it.

Here's what it should look like in Blender.
9S.png

When I try to run the script with the wmb file path as argument I get SyntaxError: invalid syntax

Would you please post a screenshot of that error so that I can see what's happening?
## Post #84
- Username: Anony
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 20, 2017 12:10 pm
- Post datetime: 2017-05-21T16:56:40+00:00
- Post Title: Re: Nier Automata

> Reply from delguoqing
>
> Would you please post a screenshot of that error so that I can see what's happening?

That's the error I get. I made sure to check that the file path was correct before trying to run the script.
[Issue.PNG](https://xentaxbackup.github.io/file/12927_Issue.PNG)
## Post #85
- Username: delguoqing
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 12, 2014 9:55 am
- Post datetime: 2017-05-23T00:17:25+00:00
- Post Title: Re: Nier Automata

> Reply from Anony
>
> delguoqing wrote:Would you please post a screenshot of that error so that I can see what's happening?

That's the error I get. I made sure to check that the file path was correct before trying to run the script.

In your case, you should execute the following command straight ahead, WITHOUT entering python interactive REPL.
C:\Python27\python.exe wmb_parser.py C:\Users\User\Desktop\rips\files\wmb\pl0000.wmb

Anyway, since many people know little about python or programming, I'll make an executable to which you can simply drag and drop. Just wait a day or two.
## Post #86
- Username: Anony
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 20, 2017 12:10 pm
- Post datetime: 2017-05-23T02:51:47+00:00
- Post Title: Re: Nier Automata

> Reply from delguoqing
>
> Anony wrote:delguoqing wrote:Would you please post a screenshot of that error so that I can see what's happening?

That's the error I get. I made sure to check that the file path was correct before trying to run the script.

In your case, you should execute the following command straight ahead, WITHOUT entering python interactive REPL.
C:\Python27\python.exe wmb_parser.py C:\Users\User\Desktop\rips\files\wmb\pl0000.wmb

Anyway, since many people know little about python or programming, I'll make an executable to which you can simply drag and drop. Just wait a day or two.

Thanks. It works now.
## Post #87
- Username: MuratG
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Oct 28, 2014 7:56 am
- Post datetime: 2017-05-23T04:00:17+00:00
- Post Title: Re: Nier Automata

thanks
## Post #88
- Username: delguoqing
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 12, 2014 9:55 am
- Post datetime: 2017-05-24T13:20:59+00:00
- Post Title: Re: Nier Automata

Hi, all, I have converted my scripts into an easy-to-use executable.

Usage:
1.drag&drop "wmb" files to model_parser.exe. A gtb file will be generated.
2.drag&drop "wtp" AND "wta" files to model_parser.exe. A bunch of textures with proper names will be generated.
3.install gtb_importer addon for Blender.
4.import "gtb" file into Blender.

NOTE: if you feed the exe only wtp files, textures will be generated, but with no proper names. You have to assign textures to meshes by hand afterwards.
P.S. Also fixed a bug of unable to import some models, e.g. pascal.
[https://www.mediafire.com/?eezbuyxn3hucnnv](https://www.mediafire.com/?eezbuyxn3hucnnv)
## Post #89
- Username: MuratG
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Oct 28, 2014 7:56 am
- Post datetime: 2017-05-27T14:21:11+00:00
- Post Title: Re: Nier Automata

> Reply from marcussacana
>
> My tools are only to .smd and .bin

the .mcd have this struct to help: http://zenhax.com/viewtopic.php?t=1502& ... witterfeed
the .mcd is the menu text i think, he do not have encryption but the text format is a shit...
He contains entries of the position of a char in the font (s0001.dat>s0001.mcd => s0001.dtt) and the "string" in the .mdc is a sequence of index of the char entry... soo, is a little shit edit this...

the .dtt is like the .dat, contains just a .dds

The .dat and .pck i sent a mediafire url in the frist page of this topic.

have the .tmd, i do not created a tool to this format, but i think is just something like this
Code: Select allstruct TMD{
int32 StrCount;
TMDEntry[] Content = new TMDEntry[StrCount];
}
struct TMDEntry{
int32 len;
byte[] Buffer = new byte[len*2];
}


anyway to the tmd i can wrote a code after...

CPK with text is: data002, data009, data012, data013, data100

i think is this:
SMD => Cutscene Subtitle
Bin => In Game Text
MCD => Menu/UI Text
DTT => A part of the .mcd, the font/texture.
TMD => I think is itens description, but looks have a general content.

--edit
Now my tool support the TMD.

Hi font (s0001.dat>s0001.mcd => s0001.dtt) where font files?
## Post #90
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2017-05-30T03:05:42+00:00
- Post Title: Re: Nier Automata

> Reply from MuratG
>
> 
Hi font (s0001.dat>s0001.mcd => s0001.dtt) where font files?
the s0001.dtt is the font, is a collection of .dds textures
## Post #91
- Username: Username1091
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 04, 2017 6:04 am
- Post datetime: 2017-06-03T22:48:46+00:00
- Post Title: Re: Nier Automata

> Reply from atvaark
>
> nenkitsune wrote:Ok, I've hit my limit. I'm trying to mess around with the BGM files, I can extract them, convert them to OGG, convert them back to WEM, but how in the hell do I repack them back into a WSP?
WSP is just a concatenation of the WEM files with 255 bytes alignment. You'll have to figure out where the offsets to each WEM is stored or you can't use files sizes bigger than the original WEMs.

Well, I had the same question, I want to make custom soundpacks, just stuck in repacking the wsp file, any idea how to do that? Thanks.
## Post #92
- Username: Vereda
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 08, 2017 12:17 pm
- Post datetime: 2017-06-08T04:23:14+00:00
- Post Title: Re: Nier Automata

> Reply from delguoqing
>
> Hi, all, I have converted my scripts into an easy-to-use executable.

Usage:
1.drag&drop "wmb" files to model_parser.exe. A gtb file will be generated.
2.drag&drop "wtp" AND "wta" files to model_parser.exe. A bunch of textures with proper names will be generated.
3.install gtb_importer addon for Blender.
4.import "gtb" file into Blender.

NOTE: if you feed the exe only wtp files, textures will be generated, but with no proper names. You have to assign textures to meshes by hand afterwards.
P.S. Also fixed a bug of unable to import some models, e.g. pascal.
https://www.mediafire.com/?eezbuyxn3hucnnv

I know from a friend that this works for the pc version but what if I have the disk for ps4? How do I access the files from the disk on my computer? 
It's my first time trying to port.
## Post #93
- Username: delguoqing
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 12, 2014 9:55 am
- Post datetime: 2017-06-08T12:26:24+00:00
- Post Title: Re: Nier Automata

> Reply from Vereda
>
> delguoqing wrote:Hi, all, I have converted my scripts into an easy-to-use executable.

Usage:
1.drag&drop "wmb" files to model_parser.exe. A gtb file will be generated.
2.drag&drop "wtp" AND "wta" files to model_parser.exe. A bunch of textures with proper names will be generated.
3.install gtb_importer addon for Blender.
4.import "gtb" file into Blender.

NOTE: if you feed the exe only wtp files, textures will be generated, but with no proper names. You have to assign textures to meshes by hand afterwards.
P.S. Also fixed a bug of unable to import some models, e.g. pascal.
https://www.mediafire.com/?eezbuyxn3hucnnv

I know from a friend that this works for the pc version but what if I have the disk for ps4? How do I access the files from the disk on my computer? 
It's my first time trying to port.
Sadly, as far as i know, there's no way you can do that.
Even if you do, there's no guarantee these tools will work for ps4 version.
## Post #94
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2017-06-08T18:03:41+00:00
- Post Title: Re: Nier Automata

Hi Delquoqing! Thanks for your great work  . But please make your script in 3ds max if possible. Thanks again.
## Post #95
- Username: Username1091
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 04, 2017 6:04 am
- Post datetime: 2017-06-09T02:17:20+00:00
- Post Title: Re: Nier Automata

> Reply from atvaark
>
> The .wsp archives can contain multiple .wem files and so can the .bnk archives.
The .wsp files don't have an index, they are just a stream of files without metadata and with alignment.

All .wem files can be extracted by parsing all the sound files (they start with the RIFF header). But ww2ogg is pretty strict about file sizes. Next to the RIFF header is the 32 bit size of the following sound file, so they can be split properly. I might upload a tool or script to split the files some time later.
I also found some .wem files in the .bnk files that overlap and can't be converted by ww2ogg.

Edit:
I managed to repair one of the corrupt .wem files inside the .bnk archive by fixing the "RIFF" header size and the "data" size. It was the first 15KB of the song "Birth of a Wish". Turns out the full size .wem file was in one of the .wsp archives.

Edit:
Here's the tool I wrote to extract all the .wem files which are not corrupt from the game's sound directory.
14997 total files can be extracted and 14974 of them can be converted to ogg via ww2ogg.

Download:
https://gist.github.com/Atvaark/680d189 ... ractor.zip

Usage example: 
Code: Select allnier-sound-extractor.exe extract -out "outdir" "E:\Games\Steam_Library\SteamApps\common\NieRAutomata\data\sound"


Excuse me, do you know how to repack the wsp file?
## Post #96
- Username: Username1091
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 04, 2017 6:04 am
- Post datetime: 2017-06-09T02:40:36+00:00
- Post Title: Re: Nier Automata

Does anyone know where all the dialogue subtitles are? I find some in data002.cpk\ph1\p100.dat but it seems only contain the subtitles from entrance to city ruins: cave. Thanks in advance.
## Post #97
- Username: Criller
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 12, 2017 9:58 pm
- Post datetime: 2017-06-12T14:21:43+00:00
- Post Title: Re: Nier Automata

> Reply from marcussacana
>
> My tools are only to .smd and .bin

the .mcd have this struct to help: http://zenhax.com/viewtopic.php?t=1502& ... witterfeed
the .mcd is the menu text i think, he do not have encryption but the text format is a shit...
He contains entries of the position of a char in the font (s0001.dat>s0001.mcd => s0001.dtt) and the "string" in the .mdc is a sequence of index of the char entry... soo, is a little shit edit this...

the .dtt is like the .dat, contains just a .dds

The .dat and .pck i sent a mediafire url in the frist page of this topic.

have the .tmd, i do not created a tool to this format, but i think is just something like this
Code: Select allstruct TMD{
int32 StrCount;
TMDEntry[] Content = new TMDEntry[StrCount];
}
struct TMDEntry{
int32 len;
byte[] Buffer = new byte[len*2];
}


anyway to the tmd i can wrote a code after...

CPK with text is: data002, data009, data012, data013, data100

i think is this:
SMD => Cutscene Subtitle
Bin => In Game Text
MCD => Menu/UI Text
DTT => A part of the .mcd, the font/texture.
TMD => I think is itens description, but looks have a general content.

--edit
Now my tool support the TMD.

Username1091 here you are
## Post #98
- Username: Criller
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 12, 2017 9:58 pm
- Post datetime: 2017-06-12T14:34:25+00:00
- Post Title: Re: Nier Automata

I'm trying to work on the MCD files so that I can remove the text that appears during the loading screens (to make them faster).

I read all the msgs and I got something. Still, with no really experience I can't do much.

The text I need to edit is in data009.cpk -> ui -> ui_chapter.dat -> messchapter.mcd according to what I found in here [https://forum.xentax.com/viewtopic.php?f=21&t=16064](https://forum.xentax.com/viewtopic.php?f=21&t=16064) (3rd post)

Lastly, thanks marcussacana, helpful
## Post #99
- Username: Criller
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 12, 2017 9:58 pm
- Post datetime: 2017-06-12T14:42:45+00:00
- Post Title: Re: Nier Automata

I also made a tool to unpack the DAT files faster using DAT tool (yeah it sucks but still, it works)

[https://www.youtube.com/watch?v=2za5A_-j4YQ](https://www.youtube.com/watch?v=2za5A_-j4YQ)
## Post #100
- Username: Criller
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 12, 2017 9:58 pm
- Post datetime: 2017-06-13T17:02:20+00:00
- Post Title: Re: Nier Automata

DTT to DDS converter

[https://www.youtube.com/watch?v=YamNdYx6pTk](https://www.youtube.com/watch?v=YamNdYx6pTk)
## Post #101
- Username: Criller
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 12, 2017 9:58 pm
- Post datetime: 2017-06-13T20:22:46+00:00
- Post Title: Re: Nier Automata

> Reply from Criller
>
> DTT to DDS converter

https://www.youtube.com/watch?v=YamNdYx6pTk

HEY! There was a bug: after the DDS was extracted, a "255" was added at the end. Now it's solved. Sorry
## Post #102
- Username: Criller
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 12, 2017 9:58 pm
- Post datetime: 2017-06-13T20:30:16+00:00
- Post Title: Re: Nier Automata

Searching a string of bytes in hundreds of files is a chore, so I made a tool to put together different files (even with different formats)

[https://drive.google.com/open?id=0B4K9P ... Gt4TG5GdFk](https://drive.google.com/open?id=0B4K9PoWYBWEgNWwzZGt4TG5GdFk)

Yeah I know, I am super-programmer
## Post #103
- Username: atvaark
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Aug 28, 2015 10:19 pm
- Post datetime: 2017-06-14T20:10:31+00:00
- Post Title: Re: Nier Automata

> Reply from Criller
>
> DTT to DDS converter

https://www.youtube.com/watch?v=YamNdYx6pTk

That looks like it incorrectly extracts only a single DDS file from DDT archives.

Example:
ui_hud.dtt contains hud.wtp and messhud.wtp which in total contain 4 dds files.
## Post #104
- Username: Criller
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 12, 2017 9:58 pm
- Post datetime: 2017-06-15T07:31:29+00:00
- Post Title: Re: Nier Automata

> Reply from atvaark
>
> Criller wrote:DTT to DDS converter

https://www.youtube.com/watch?v=YamNdYx6pTk

That looks like it incorrectly extracts only a single DDS file from DDT archives.

Example:
ui_hud.dtt contains hud.wtp and messhud.wtp which in total contain 4 dds files.

... I didnt know that... I suppose I got to fix it

- edit -

According to this [https://gist.github.com/Wunkolo/213aa61 ... ebb8ab89c2](https://gist.github.com/Wunkolo/213aa61eb0c874172aec97ebb8ab89c2) there could be even other format of files... Good luck with it, I was here asking for a mod
## Post #105
- Username: bluelovers
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 12, 2017 3:53 pm
- Post datetime: 2017-06-16T04:02:11+00:00
- Post Title: Re: Nier Automata

anyway for make font file?

that looks like dds font

but i don't know how to make _tb/ftb/wta file
## Post #106
- Username: wardialer6000
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 09, 2016 2:05 am
- Post datetime: 2017-06-16T18:44:25+00:00
- Post Title: Re: Nier Automata

intel GPA graphics frame analyzer works with this game... in both T-posed (IA) and posed (VS).  i usually just care about the meshes since i'm gonna print the models, but textures seem to be there and exportable to DDS.  i'm not sure this helps anyone... but here are some screenshots below.
## Post #107
- Username: aylz00
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 17, 2017 1:17 pm
- Post datetime: 2017-06-17T05:26:30+00:00
- Post Title: Re: Nier Automata

> Reply from delguoqing
>
> Hi, all, I have converted my scripts into an easy-to-use executable.

Usage:
1.drag&drop "wmb" files to model_parser.exe. A gtb file will be generated.
2.drag&drop "wtp" AND "wta" files to model_parser.exe. A bunch of textures with proper names will be generated.
3.install gtb_importer addon for Blender.
4.import "gtb" file into Blender.

NOTE: if you feed the exe only wtp files, textures will be generated, but with no proper names. You have to assign textures to meshes by hand afterwards.
P.S. Also fixed a bug of unable to import some models, e.g. pascal.
https://www.mediafire.com/?eezbuyxn3hucnnv
Hello, my English is very bad. I am using google translation to communicate with you. Could you please create a script or tool that wraps wmb? I would like to modify the Nier model in the game. Look at your ID like the Chinese people. Can I use Chinese to communicate with you? My E-mail address is [48357269@qq.com](mailto:48357269@qq.com)
## Post #108
- Username: midghost
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 14, 2017 6:45 am
- Post datetime: 2017-06-17T17:32:31+00:00
- Post Title: Re: Nier Automata

> Reply from bluelovers
>
> anyway for make font file?

that looks like dds font

but i don't know how to make _tb/ftb/wta file
i can create ftb(font table) and dds, but without corresponding wta, they are all useless.
## Post #109
- Username: Shivalee
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 19, 2017 12:21 am
- Post datetime: 2017-06-18T16:30:06+00:00
- Post Title: Re: Nier Automata

> Reply from delguoqing
>
> Hi, all, I have converted my scripts into an easy-to-use executable.

Usage:
1.drag&drop "wmb" files to model_parser.exe. A gtb file will be generated.
2.drag&drop "wtp" AND "wta" files to model_parser.exe. A bunch of textures with proper names will be generated.
3.install gtb_importer addon for Blender.
4.import "gtb" file into Blender.

NOTE: if you feed the exe only wtp files, textures will be generated, but with no proper names. You have to assign textures to meshes by hand afterwards.
P.S. Also fixed a bug of unable to import some models, e.g. pascal.
https://www.mediafire.com/?eezbuyxn3hucnnv

When trying to export the .gtb file in blender to XNAlara format I get the error:

AttributeError: 'NonType' Object has no attribute 'filepath'

I have no idea what this means or how to fix it. I can't take a screenshot since the error message disappears before I can take one.
So far, I've tried the latest version of Blender 2.78 and earlier versions of 2.7
## Post #110
- Username: Lexicona
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 24, 2017 2:39 am
- Post datetime: 2017-06-23T18:59:31+00:00
- Post Title: Re: Nier Automata

Hey everyone, I'm currently on a fairly small window of time, so if this could be resolved in the next week, that'd be great.  I'll constantly be checking the forum too, so that' son my end.

I'm having trouble with the sound files and programs that were provided.  I've found the sound files that i wish to rip from WSP, my issue however is it feels like the programs aren't doing anything, and i'm fairly sure that i'm improperly implementing them for them to actually work.  How exactly are the files, like nier sound extractor, supposed to work or be used?  Please provide an example or some frame of reference.
## Post #111
- Username: kasake
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Feb 16, 2012 3:03 pm
- Post datetime: 2017-07-08T08:42:40+00:00
- Post Title: Re: Nier Automata

> Reply from delguoqing
>
> Hi, all, I have converted my scripts into an easy-to-use executable.

Usage:
1.drag&drop "wmb" files to model_parser.exe. A gtb file will be generated.
2.drag&drop "wtp" AND "wta" files to model_parser.exe. A bunch of textures with proper names will be generated.
3.install gtb_importer addon for Blender.
4.import "gtb" file into Blender.

NOTE: if you feed the exe only wtp files, textures will be generated, but with no proper names. You have to assign textures to meshes by hand afterwards.
P.S. Also fixed a bug of unable to import some models, e.g. pascal.
https://www.mediafire.com/?eezbuyxn3hucnnv

Is there a special version of blender that you need for the gtb_importer addon to work? I can't get blender to install the addon. :/

EDIT: To give some context as to how I'm going about how to do this. I'm running on the latest 64bit version of Blender. I attempt to install gtb_importer.py via "user preferences > addon > install from file"
After doing all that, I do a search of "gtb" in my addons to enable, however I do not see the addon added. I go to file > import, and I don't see it there either.

I've tried installing a 32bit version of blender and it doesn't seem to solve the issue. BTW I'm running on Windows 10 64bit. I've been at this for days and it's killing me. Any help is appreciated!
## Post #112
- Username: delguoqing
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 12, 2014 9:55 am
- Post datetime: 2017-07-10T05:09:38+00:00
- Post Title: Re: Nier Automata

> Reply from Shivalee
>
> 
When trying to export the .gtb file in blender to XNAlara format I get the error:

AttributeError: 'NonType' Object has no attribute 'filepath'

I have no idea what this means or how to fix it. I can't take a screenshot since the error message disappears before I can take one.
So far, I've tried the latest version of Blender 2.78 and earlier versions of 2.7

If you have got the model imported in Blender, then the problem resides in your "blender to XNAlara".
I have no experience in XNAlara, so I'm afraid I can't help.
## Post #113
- Username: delguoqing
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 12, 2014 9:55 am
- Post datetime: 2017-07-10T05:14:08+00:00
- Post Title: Re: Nier Automata

> Reply from kasake
>
> 

Is there a special version of blender that you need for the gtb_importer addon to work? I can't get blender to install the addon. :/

EDIT: To give some context as to how I'm going about how to do this. I'm running on the latest 64bit version of Blender. I attempt to install gtb_importer.py via "user preferences > addon > install from file"
After doing all that, I do a search of "gtb" in my addons to enable, however I do not see the addon added. I go to file > import, and I don't see it there either.

I've tried installing a 32bit version of blender and it doesn't seem to solve the issue. BTW I'm running on Windows 10 64bit. I've been at this for days and it's killing me. Any help is appreciated!
I'm currently using Blender 2.78 64bit, but I guess 32bit should be ok too.
To install the addon, just put the whole "gtb_importer" folder in xxxxx\Blender Foundation\Blender\2.78(your version)\scripts\addon.
## Post #114
- Username: kasake
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Feb 16, 2012 3:03 pm
- Post datetime: 2017-07-16T16:07:02+00:00
- Post Title: Re: Nier Automata

> Reply from delguoqing
>
> kasake wrote:

Is there a special version of blender that you need for the gtb_importer addon to work? I can't get blender to install the addon. :/

EDIT: To give some context as to how I'm going about how to do this. I'm running on the latest 64bit version of Blender. I attempt to install gtb_importer.py via "user preferences > addon > install from file"
After doing all that, I do a search of "gtb" in my addons to enable, however I do not see the addon added. I go to file > import, and I don't see it there either.

I've tried installing a 32bit version of blender and it doesn't seem to solve the issue. BTW I'm running on Windows 10 64bit. I've been at this for days and it's killing me. Any help is appreciated!
I'm currently using Blender 2.78 64bit, but I guess 32bit should be ok too.
To install the addon, just put the whole "gtb_importer" folder in xxxxx\Blender Foundation\Blender\2.78(your version)\scripts\addon.

Ah I actually found out it's because the addon is called "Import-Export: Game To Blender Format". I just kept searching for "gtb", which yielded no results... /facepalm

Thanks for your help!
## Post #115
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2017-07-19T20:25:07+00:00
- Post Title: Re: Nier Automata

Hello, delquoqing! Is it possible that you make a script for 3ds max or noesis??? It will be great! Thanks.
## Post #116
- Username: Chisa Makimura
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Sep 25, 2017 9:24 am
- Post datetime: 2017-09-25T03:03:06+00:00
- Post Title: Re: Nier Automata

> Reply from atvaark
>
> The .wsp archives can contain multiple .wem files and so can the .bnk archives.
The .wsp files don't have an index, they are just a stream of files without metadata and with alignment.

All .wem files can be extracted by parsing all the sound files (they start with the RIFF header). But ww2ogg is pretty strict about file sizes. Next to the RIFF header is the 32 bit size of the following sound file, so they can be split properly. I might upload a tool or script to split the files some time later.
I also found some .wem files in the .bnk files that overlap and can't be converted by ww2ogg.

Edit:
I managed to repair one of the corrupt .wem files inside the .bnk archive by fixing the "RIFF" header size and the "data" size. It was the first 15KB of the song "Birth of a Wish". Turns out the full size .wem file was in one of the .wsp archives.

Edit:
Here's the tool I wrote to extract all the .wem files which are not corrupt from the game's sound directory.
14997 total files can be extracted and 14974 of them can be converted to ogg via ww2ogg.

Download:
https://gist.github.com/Atvaark/680d189 ... ractor.zip

Usage example: 
Code: Select allnier-sound-extractor.exe extract -out "outdir" "E:\Games\Steam_Library\SteamApps\common\NieRAutomata\data\sound"

Hey i have been getting the failed to export file at offset how do i fix it 


test1.png (80.73 KiB) Viewed 241 times
## Post #117
- Username: Chisa Makimura
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Sep 25, 2017 9:24 am
- Post datetime: 2017-09-25T03:10:05+00:00
- Post Title: Re: Nier Automata

test2.png (86.41 KiB) Viewed 241 times
## Post #118
- Username: atvaark
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Aug 28, 2015 10:19 pm
- Post datetime: 2017-09-28T22:07:37+00:00
- Post Title: Re: Nier Automata

> Reply from Chisa Makimura
>
> atvaark wrote:The .wsp archives can contain multiple .wem files and so can the .bnk archives.
The .wsp files don't have an index, they are just a stream of files without metadata and with alignment.

All .wem files can be extracted by parsing all the sound files (they start with the RIFF header). But ww2ogg is pretty strict about file sizes. Next to the RIFF header is the 32 bit size of the following sound file, so they can be split properly. I might upload a tool or script to split the files some time later.
I also found some .wem files in the .bnk files that overlap and can't be converted by ww2ogg.

Edit:
I managed to repair one of the corrupt .wem files inside the .bnk archive by fixing the "RIFF" header size and the "data" size. It was the first 15KB of the song "Birth of a Wish". Turns out the full size .wem file was in one of the .wsp archives.

Edit:
Here's the tool I wrote to extract all the .wem files which are not corrupt from the game's sound directory.
14997 total files can be extracted and 14974 of them can be converted to ogg via ww2ogg.

Download:
https://gist.github.com/Atvaark/680d189 ... ractor.zip

Usage example: 
Code: Select allnier-sound-extractor.exe extract -out "outdir" "E:\Games\Steam_Library\SteamApps\common\NieRAutomata\data\sound"

Hey i have been getting the failed to export file at offset how do i fix it
You can fix most of the corrupt files by changing their size after the RIFF WAVE header (they're truncated for some reason). But they're mostly duplicates by the way.
## Post #119
- Username: Chisa Makimura
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Sep 25, 2017 9:24 am
- Post datetime: 2017-10-23T00:08:04+00:00
- Post Title: Re: Nier Automata

Usage example: 
```
nier-sound-extractor.exe extract -out "outdir" "E:\Games\Steam_Library\SteamApps\common\NieRAutomata\data\sound"
```
[/quote]

Hey i have been getting the failed to export file at offset how do i fix it[/quote]
You can fix most of the corrupt files by changing their size after the RIFF WAVE header (they're truncated for some reason). But they're mostly duplicates by the way.[/quote]

it seems your program does not work any more! 


Untitledhelp.png (98.53 KiB) Viewed 192 times
## Post #120
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-10-28T18:01:27+00:00
- Post Title: Re: Nier Automata

...
[Hoe.PNG](https://xentaxbackup.github.io/file/13501_Hoe.PNG)
## Post #121
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-10-28T18:11:50+00:00
- Post Title: Re: Nier Automata

...
## Post #122
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-10-28T18:12:50+00:00
- Post Title: Re: Nier Automata

This are my questions:
## Post #123
- Username: Chisa Makimura
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Sep 25, 2017 9:24 am
- Post datetime: 2017-11-09T01:37:37+00:00
- Post Title: Re: Nier Automata

> Reply from yarrmateys
>
> SirZephy wrote:however, these .wsp files/archives are at least 30MB large and are being converted down to 2-5MB audio files so I'm not sure if these .wsp files contain more than one audio file in them?
yeah, they do. they contain multiple file headers. they probably need to be split first.

edit: a quickbms script to do it.
Code: Select allfindloc OFFSET string "RIFF"
do
    goto OFFSET
    get DUMMY long
    findloc NEXT_OFFSET string "RIFF" 0 ""
    if NEXT_OFFSET == ""
        get SIZE asize
    else
        math SIZE = NEXT_OFFSET
    endif
    math SIZE -= OFFSET
    log "" OFFSET SIZE
    math OFFSET = NEXT_OFFSET
while NEXT_OFFSET != ""

just select every wsp file when it asks you for source, it'll output every file's contents into separate folders.

if you combine all the wem and wsp files into one using copy /b command, it'll be even easier. the single file that'll result from that will output everything inside of it in an ordered way into the same folder without any need for messing with moving, folders, files, filenames and such.

after combining this with your stuff i got over 400 files out of it.

I did this but all i have now is .wav files that dont work what do i do now
## Post #124
- Username: Rindera
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 13, 2018 2:26 pm
- Post datetime: 2018-03-13T06:56:25+00:00
- Post Title: Re: Nier Automata

So... Russian project is dropped. I've read the whole in-game text and corrected an enormous number of errors and typos. The team included those into the game and they do not want to do anything more. They don't share tools as well.
And now I'm in search of any tools or people that can help me to finish the translation. I've read the thread and not clearly understand if the tools exist or there are only ripped pieces of code. I'm not a programmer so it is pretty tough.
Now my friend is rewriting this [https://github.com/micktu/att](https://github.com/micktu/att) tool because it's bugged and works only in win8+. So I think this is not a problem. But I don't have ANY tools to work with the interface texts and fonts.
Any help?
## Post #125
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2018-06-11T16:22:35+00:00
- Post Title: Re: Nier Automata

Thanks to delguoqing and DEElekgolo and everybody I forgot to mention (sorry about that) work on the model format I have implemented support for Nier Automata's model to my noesis plugin. It is including animation support as the animation format used is identical to Bayonetta 2. Notice that material are only texture + normal map for now.
I have found several new vertex formats while doing so and I described them in the binary templates located here:
[https://github.com/Kerilk/bayonetta_too ... _templates](https://github.com/Kerilk/bayonetta_tools/tree/master/binary_templates)

You can find the plugin here:
[https://github.com/Kerilk/noesis_bayonetta_pc](https://github.com/Kerilk/noesis_bayonetta_pc)
in the release section.

What you should get (Once you disable the armor meshes using the Data Viewer tool):
## Post #126
- Username: eraser3000
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 10, 2018 1:13 am
- Post datetime: 2018-10-09T17:15:51+00:00
- Post Title: Re: Nier Automata

i've read a few times the pages regarding audio extraction from the wsp files, and still i don't manage to exrtact it properly - or i just get 1 working ogg file, or the entire extracted wsp has non working wav -, someone managed to make it work? i'd like to create a mod regarding orchestral tracks rather tna normal ones
## Post #127
- Username: Aphasia
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 11, 2017 7:37 pm
- Post datetime: 2018-12-08T23:53:49+00:00
- Post Title: Re: Nier Automata

Hello, 

Is anyone still interested in modding this game?

Also, to contribute here is a function I reversed from the game.

```
Used to convert from object id to object name
*/
struct ObjectIdConvert
{
	int m_ObjectIdBase;
	const char* m_szPrefix;
};

BOOL __fastcall ObjectIdToObjectName(char*szObjectName, size_t size, int objectId)
{
	static char HexChars[] = { '0', '1', '2', '3', '4', '5', '6', '7', '8', '9', 'a', 'b', 'c', 'd', 'e', 'f' };
	static ObjectIdConvert Converts[] = { { 0x10000, "pl" }, { 0x20000, "em" }, { 0x30000, "wp" }, { 0x40000, "et" }, { 0x50000, "ef" }, { 0x60000, "es" },
										{ 0x70000, "it" }, { 0x90000, "sc" }, { 0xA0000, "um" }, { 0xC0000, "bg" }, { 0xE0000, "bh" }, { 0xF0000, "ba" } };

	const char* szName;
	unsigned int i = 0;

	do
	{
		if (Converts[i].m_ObjectIdBase == (objectId & 0xFFFF0000)) // high word of the int
		{
			szObjectName[0] = Converts[i].m_szPrefix[0];
			szObjectName[1] = Converts[i].m_szPrefix[1];
			szObjectName[2] = HexChars[((signed __int64)objectId >> 12) & 0xF];
			szObjectName[3] = HexChars[((signed __int64)objectId >> 8) & 0xF];
			szObjectName[4] = HexChars[((signed __int64)objectId >> 4) & 0xF];
			szObjectName[5] = HexChars[objectId & 0xF];
			szObjectName[6] = 0; //null terminatior
			return TRUE;
		}
		++i;
	} while (i < ARRAYSIZE(Converts));

	memset(szObjectName, 0, size);

	if (objectId == -1)
	{
		strcpy_s(szObjectName, size, "eObjInvalid");
		return FALSE;
	}
	else
	{
		strcpy_s(szObjectName, size, (objectId != 0x700000) ? "Unknow" : "Null");
		return FALSE;
	}
}

```
## Post #128
- Username: Irastris
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 21, 2015 12:28 pm
- Post datetime: 2019-01-10T01:28:08+00:00
- Post Title: Re: Nier Automata

Due to the large size of the archives, I hope someone can answer my question before I get started and potentially waste my time.

Is it possible to import NieR Automata's maps, and if so how would I do so? Are the maps stored in the same format as rigged characters?

Thank you.
## Post #129
- Username: Novarek
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 17, 2019 9:52 am
- Post datetime: 2019-06-17T22:09:15+00:00
- Post Title: Re: Nier Automata

> Reply from Kerilk ↑Tue Jun 12, 2018 12:22 am at Tue Jun 12, 2018 12:22 am
>
> 
Thanks to delguoqing and DEElekgolo and everybody I forgot to mention (sorry about that) work on the model format I have implemented support for Nier Automata's model to my noesis plugin. It is including animation support as the animation format used is identical to Bayonetta 2. Notice that material are only texture + normal map for now.
I have found several new vertex formats while doing so and I described them in the binary templates located here:
https://github.com/Kerilk/bayonetta_too ... _templates

You can find the plugin here:
https://github.com/Kerilk/noesis_bayonetta_pc
in the release section.

What you should get (Once you disable the armor meshes using the Data Viewer tool):

Work perfectly for the model, sadly each attempt of exporting the animation result on an instant crash (ran out of memory error).

EDIT: problem solved, just had to split and repack the .mot file into several (and lighter) .dat file, export work flawlesly after that
## Post #130
- Username: Slozhny
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Aug 31, 2009 6:03 am
- Post datetime: 2019-09-11T09:17:22+00:00
- Post Title: Re: Nier Automata

> Reply from Novarek ↑Tue Jun 18, 2019 6:09 am at Tue Jun 18, 2019 6:09 am
>
> 



Work perfectly for the model, sadly each attempt of exporting the animation result on an instant crash (ran out of memory error).

EDIT: problem solved, just had to split and repack the .mot file into several (and lighter) .dat file, export work flawlesly after that

How did you repack of *.dat???
## Post #131
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2019-09-11T17:19:19+00:00
- Post Title: Re: Nier Automata

If you can use Linux ( Ubuntu for  Windows is fine) you can use the tools there: [https://github.com/Kerilk/bayonetta_tools](https://github.com/Kerilk/bayonetta_tools)

You should also be able to use the tools using Ruby for Windows but I haven't done so in a long time.
## Post #132
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2019-10-03T21:24:22+00:00
- Post Title: Re: Nier Automata

> Reply from Kerilk ↑Thu Sep 12, 2019 1:19 am at Thu Sep 12, 2019 1:19 am
>
> 
If you can use Linux ( Ubuntu for  Windows is fine) you can use the tools there: https://github.com/Kerilk/bayonetta_tools

You should also be able to use the tools using Ruby for Windows but I haven't done so in a long time.

I managed to unpack 2B's animation dat, but I've been having problems getting it repacked.
I tried using ruby, but the "sudo" command on the bayonetta tools page doesn't work because I'm not running Linux (I'm running windows. That and the Libbin gem seemed to have trouble installing)
I tried using this python script too [https://github.com/xxk-i/DATrepacker](https://github.com/xxk-i/DATrepacker) but it only produced this error:


her dat and dtt files if needed [https://www.mediafire.com/file/kzkda0px ... 0.zip/file](https://www.mediafire.com/file/kzkda0pxmsmbocb/pl0000.zip/file)
## Post #133
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2019-10-08T04:22:55+00:00
- Post Title: Re: Nier Automata

Yes I imagine the libbin gem might prove problematic on windows as it needs a working compiler. I you want to install linux on windows you can do so using this Microsoft tutorial:

[https://docs.microsoft.com/en-us/window ... tall-win10](https://docs.microsoft.com/en-us/windows/wsl/install-win10)

If you want to keep trying ruby for windows, then you need to install the dev kit:
[https://rubyinstaller.org/add-ons/devkit.html](https://rubyinstaller.org/add-ons/devkit.html)

Edit: I just tested the tools using ruby for windows and managed to install everything. The only tool that should not be functional is the assimp exporter/importer for bayonetta/bayo 2 etc... models. Using ruby for windows I extracted and repacked a dat file without issue.
## Post #134
- Username: Alvare
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 28, 2017 3:45 pm
- Post datetime: 2020-01-16T14:56:03+00:00
- Post Title: Re: Nier Automata

Eh.. Can anyone please explain me how to get the dat and dtt extracted? I don't know what to do with the dat tool..
It's giving me a main.cpp and dat.md. Can I execute that within Blender or something? Or do I need to compile and run it from another software?
## Post #135
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2020-01-17T05:26:23+00:00
- Post Title: Re: Nier Automata

From Urser Bayonetta model swap tutorial:

[https://steamcommunity.com/sharedfiles/ ... 1178661446](https://steamcommunity.com/sharedfiles/filedetails/?id=1178661446)

> .dat decompiler/recomplier
>
> 
>
>     PlatinumDat.exe https://drive.google.com/file/d/0B87z-- ... 9mV0U/view (included in Bayonetta Audio Tools) (credits to Skyth and Mario Tainaka)

This one is usually quite user-friendly unless you want to repack dat files with content of modified size.
## Post #136
- Username: DevolasRevenge
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 15, 2020 1:25 am
- Post datetime: 2020-06-04T22:19:57+00:00
- Post Title: Re: Nier Automata

Hey guys, It's great seeing all these posts from 3 years ago, how people all worked on deceiphering the way that files are read. I don't know too much about digging myself but I wish I was here 3 years ago instead of discovering the game last year. If anyone is still interesting in the game we have a NieR A modding discord, it isn't too active but there are a few of us still making mods. Someone has even made a Blender Add-on for unpacking DATs/DTTs as well as importing & exporting them. Our discord is here: [https://discord.gg/yxvMxq2](https://discord.gg/yxvMxq2)
## Post #137
- Username: bortoloti
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 11, 2021 7:45 pm
- Post datetime: 2023-03-20T17:58:51+00:00
- Post Title: Re: Nier Automata

Sorry for my bad english and reopening this topic after all these years. I would like someone to help me with the game source files. Inside the UI folder for example, I have the ui_title_us.dat and ui_title_us.dtt files, the .dat file contains the texts and the .dtt file contains the font file that I want to modify.
I would like someone to explain in a simple and objective way how I unzip the .dtt, modify it and then pack it. Thanks a lot to anyone who can help.
