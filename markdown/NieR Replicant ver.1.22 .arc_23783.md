## Post #1
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2021-04-23T17:41:37+00:00
- Post Title: NieR Replicant ver.1.22 .arc

Can someone help with new NieR Replicant game? There is a few arc archives.
A few examples - [https://disk.yandex.ru/d/da5YuGsCEZZyIw](https://disk.yandex.ru/d/da5YuGsCEZZyIw)
## Post #2
- Username: vvampii
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 12, 2019 12:37 pm
- Post datetime: 2021-04-23T21:16:37+00:00
- Post Title: NieR Replicant ver.1.22 .arc

using Zstandard (.arc > .arc.zst) requires password
[Безымянный.png](https://xentaxbackup.github.io/file/19944_Безымянный.png)
## Post #3
- Username: vvampii
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 12, 2019 12:37 pm
- Post datetime: 2021-04-24T09:29:12+00:00
- Post Title: NieR Replicant ver.1.22 .arc

more examples (.arc & .arc.zst) + .exe: [https://disk.yandex.ru/d/azCHDeM2gBLrkQ?w=1](https://disk.yandex.ru/d/azCHDeM2gBLrkQ?w=1)
might need to check .exe file for password ? common.arc has 'library (in game room)' associated files/lines inside.

> /a_center_library_01_base/mtl_book01_1nier00_village01_tjblock_002_a6stivy_001chandelierktpicturewoodwalltjmetalsttablewa1ktmarbl4carpet0kt43glass2ceilingwall_2multi_pg0out
>
> /bg/a_center_library_01_base/tex__base
## Post #4
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2021-04-24T18:34:00+00:00
- Post Title: NieR Replicant ver.1.22 .arc

> Reply from rotteneyed ↑Sat Apr 24, 2021 5:16 am at Sat Apr 24, 2021 5:16 am
>
> 
using Zstandard (.arc > .arc.zst) requires password

Hmm, Zstd doesn't seem to use passwords though, at least the dev headers don't seem to have a mention of them ([https://github.com/facebook/zstd/blob/dev/lib/zstd.h](https://github.com/facebook/zstd/blob/dev/lib/zstd.h))

Using "zstd.exe -d info.arc -o info.dec" seemed to run fine for the dlc\dlc01\info.arc file, decompressed file format is very weird though, not sure if it's actually decompressed properly.

(zstd.exe from [https://github.com/facebook/zstd/releas ... -win64.zip](https://github.com/facebook/zstd/releases/download/v1.4.9/zstd-v1.4.9-win64.zip))

Fails with every other .arc I tried with though, 'File "dlc01.arc" not compressed by zstd' or 'zstd: dlc01.arc: unsupported format', but it has the same header as the info.arc that worked so dunno what's going on there. Is there a Zstd variant that uses extra algos or something dumb like that?

E: oh, zstd.exe seems to work with the common.arc too, decompresses to ~30MB file that seems to make more sense than the info.arc I tried. Still no luck with larger files though.
## Post #5
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-04-24T19:39:45+00:00
- Post Title: NieR Replicant ver.1.22 .arc

Yeah, there's no password protection, it's just pure ZSTD from the few sample files I've looked at that people have posted.

The files info.arc and common.arc are both 1 single block of compressed data, whereas others like lang1.arc and lang2.arc are made up of small blocks of compressed data that have to be read separately.

info.arc contains the master list for all archives.  Some of them, like common.arc need to be decompressed first as the file table in info.arc references the decompressed offsets, but for others like lang1.arc it references the individual compressed sections.

Once the files from common.arc are extracted, they contain what seems like thousands of file tables that refer to other data archives.

At least that's what it seems like!
## Post #6
- Username: DaniKH
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Oct 11, 2018 5:15 am
- Post datetime: 2021-04-24T21:09:12+00:00
- Post Title: NieR Replicant ver.1.22 .arc

The sample files they shared arent really important if we want just the models. They are inside of stream.arc, but its too heavy, impossible to upload somewhere.

So, anyone had any idea about how to extract the assets files inside stream.arc? I tried with many arc unpacker tools but nothing works
## Post #7
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-04-24T21:36:06+00:00
- Post Title: NieR Replicant ver.1.22 .arc

Like I mentioned, the sample files *are* important because info.arc contains the file table which has several thousand entries for stream.arc.  So you need that to get the offsets and sizes for all of the individual files in stream.arc, easier than ripping them manually.

I've managed to parse the info.arc file table, but I don't have stream.arc to test it with at the moment (as it's probably about 13 GB), so here's an example of some entries that reference stream.arc (offset/size/filename).  They aren't in any particular order in the file table.  I assume these are meshes by the filnames.

0x0000000000580b00      0x0000000000041c5c      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_house06
0x00000000004aa7d0      0x00000000000249ad      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_house04
0x00000000004cf180      0x00000000000b197d      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_house05
0x0000000000408070      0x0000000000060cad      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_house02
0x0000000000468d20      0x0000000000041ab0      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_house03
0x00000000003cef60      0x0000000000039105      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_house01
0x0000000000385da0      0x00000000000491b2      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_entrance01
0x000000000081bd40      0x000000000001a72f      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_pg001
0x00000000007b7c90      0x00000000000640aa      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_pg000
0x0000000000106690      0x00000000001632ba      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_cliff01
0x0000000000269950      0x000000000004bbaf      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_cliff02
0x00000000002b5500      0x00000000000d0894      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_cliff03
0x0000000000027820      0x00000000000dee6c      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_bridge_cliff_01
0x000000000084f010      0x00000000000047f0      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_shadow
0x00000000005c2760      0x00000000001f390f      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_obj01
0x00000000007b6070      0x0000000000001c1e      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_obj02
0x0000000000836470      0x00000000000133b7      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_scaff01
0x0000000000849830      0x00000000000057db      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_scaff02
0x0000000000000000      0x0000000000009ff6      bg/a_cliff_village_01/a_cliff_village_01_base/msh_a_cliff_village_01_base
0x000000000000a000      0x000000000001d820      bg/a_cliff_village_01/a_cliff_village_01_base/msh_spl_bridge_bag_01
0x0000000000853800      0x000000000920b240      bg/a_cliff_village_01/a_cliff_village_01_base/tex_a_cliff_village_01_base
## Post #8
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2021-04-24T23:05:32+00:00
- Post Title: NieR Replicant ver.1.22 .arc

> Reply from DKDave ↑Sun Apr 25, 2021 5:36 am at Sun Apr 25, 2021 5:36 am
>
> 
Like I mentioned, the sample files *are* important because info.arc contains the file table which has several thousand entries for stream.arc.  So you need that to get the offsets and sizes for all of the individual files in stream.arc, easier than ripping them manually.

I've managed to parse the info.arc file table, but I don't have stream.arc to test it with at the moment (as it's probably about 13 GB), so here's an example of some entries that reference stream.arc (offset/size/filename).  They aren't in any particular order in the file table.  I assume these are meshes by the filnames.

Just checked stream.arc and looks like you're on the money  Offsets point to zstd chunks, all seem to decompress fine with zstd.exe into some "PACK" format, upped the zstd chunks here if you want to look into them: [https://bayfiles.com/vcoeU9s6uf/stream_arc_samples_zip](https://bayfiles.com/vcoeU9s6uf/stream_arc_samples_zip)

E: If anyone is interested in the audio/video files, NSACloud has made a tool for extracting/repacking those here: [https://github.com/NSACloud/NieR-Audio-Tools](https://github.com/NSACloud/NieR-Audio-Tools)
Sadly seems the audio/video pcks are much different to the main ones we've been discussing here, nice to see such quick progress though, guess we won't have to wait long for soundtrack mods
## Post #9
- Username: vvampii
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 12, 2019 12:37 pm
- Post datetime: 2021-04-24T23:14:29+00:00
- Post Title: NieR Replicant ver.1.22 .arc

> Reply from DKDave ↑Sun Apr 25, 2021 5:36 am at Sun Apr 25, 2021 5:36 am
>
> 
I've managed to parse the info.arc file table, but I don't have stream.arc to test it with at the moment (as it's probably about 13 GB)

stream.arc is about 12 gb. also there is init.arc which is about 8 gb (and it might be somewhat similar to stream or maybe common/info) 
i will try to upload some ofthese somewhere along with dlc01.arc & its info.arc

upd - init + dlc01: [https://disk.yandex.ru/d/fMGTicYB14Q6Iw?w=1](https://disk.yandex.ru/d/fMGTicYB14Q6Iw?w=1)
## Post #10
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2021-04-25T17:37:12+00:00
- Post Title: NieR Replicant ver.1.22 .arc

info.arc:
0x48 - number of files (4)
0x138 - table start offset (offset, size and etc.)

single block size is 28 bytes:
4 - unknown
4 - name offset
4 - offset*16
4 - compressed size
4 - uncompressed size
4 - unknown (usually zero)
1 - arc ID (0 - lang1.arc, 1 - lang2.arc, 2 - common.arc, 3 - param.arc, 4 - init.arc, 5 - stream.arc)
1 - flag (Compression 0 or 1)
2 - skip (40 40)

filenames...
## Post #11
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-04-25T18:10:57+00:00
- Post Title: NieR Replicant ver.1.22 .arc

@LinkOFF, some extra info that might be useful for info.arc:

* All offsets are relative to the address where that offset is stored *

Main header - 0x14 bytes:

0 - Text - "BXON"
4 - ?
8 - ?
12 - Int - Offset to archive name/type ("tpArchiveFileParam" in this case - other types seem to have different data layouts)
16 - Int - Offset to archive info header

Archive info header - 0x10 bytes:

0 - Int - Number of main archives
4 - Int - Offset to archive table
8 - Int - Total number of files in the file table
12 - Int - Offset to file table

Archive table - 0xc bytes per entry:

0 - Int - Offset to archive filename
4 - Int - ?
8 - Byte - Flags: 0 = offsets refer to uncompressed archive, 1 = offsets refer to separate ZSTD compressed files, 2 = ?)
9 -
10 - 
11 -

File table - 0x1c bytes per entry:

0 - Int - ?
4 - Int - Offset to filename
8 - Int - File offset (*16 as previously mentioned)
12 - Int - File size
16 - Int - ?
20 - Int - ?
24 - Byte - archive index number
25 - Byte - Flags
26 - Byte
27 - Byte
## Post #12
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2021-04-25T22:12:29+00:00
- Post Title: NieR Replicant ver.1.22 .arc

010 template for PACK containers, doesn't seem like there's any compression used (besides the zstd covering the whole PACK), but haven't checked with many files yet.

```
{
    DWORD Magic; // 'PACK'
    DWORD Version; // 4 in Nier
    DWORD PackSize;
    DWORD UnkData_Offset; // Offset to some unknown/encrypted data, sometimes looks like floats - offset from base of header

    DWORD Unk10; // value seems to scale with PackSize

    DWORD NameCount;
    DWORD NameTableOffset;

    DWORD Table1_FileCount;
    DWORD Table1_Offset;

    DWORD Table2_FileCount;
    DWORD Table2_Offset;
};

typedef struct 
{
    local long pos = FTell();

    DWORD NameHash;
    DWORD NameOffset;
    DWORD Unk8;

    local long endPos = FTell();

    FSeek(pos + 0x4 + NameOffset); // 0x4 = offset of NameOffset field
    string FileName;
    FSeek(endPos);
} PACK_NameEntry<read=ReadPACK_NameEntry>;

typedef struct
{
    local long pos = FTell();

    DWORD NameHash;
    DWORD NameOffset;
    DWORD DataLength;
    DWORD DataOffset;
    DWORD ErrorOffset; // offset to some weird error string, maybe is set to something besides error on some files...

    local long endPos = FTell();

    FSeek(pos + 0x4 + NameOffset); // 0x4 = offset of NameOffset field
    string FileName;

    FSeek(pos + 0xC + DataOffset);
    BYTE Data[DataLength] <optimize=false>;

    // ErrorOffset is sometimes set to 0x80XXXXXX, no idea what purpose of it is yet
    if(ErrorOffset < 0x80000000) {
        FSeek(pos + 0x10 + ErrorOffset);
        BYTE StringLength;
        char String[StringLength] <optimize=false>;
    }

    FSeek(endPos);
} PACK_FileEntry<read=ReadPACK_FileEntry>;

// funcs to let template window show names next to entry
string ReadPACK_NameEntry(PACK_NameEntry& entry)
{
    return entry.FileName;
}

string ReadPACK_FileEntry(PACK_FileEntry& entry)
{
    return entry.FileName;
}

// Seperate struct so files can be collapsed in template window
struct PACK_NameTable(int NameCount)
{
    PACK_NameEntry Entries[NameCount] <optimize=false>;
};

struct PACK_FileTable(int FileCount)
{
    PACK_FileEntry Entries[FileCount] <optimize=false>;
};

PACK_Header Header;

FSeek(Header.NameTableOffset + 0x18); // 0x18 = offset of NameTableOffset field
if(Header.NameCount > 0)
    PACK_NameTable Names(Header.NameCount);

// Table1/Table2 seem to share same struct
FSeek(Header.Table1_Offset + 0x20);
if (Header.Table1_FileCount > 0)
    PACK_FileTable Table1(Header.Table1_FileCount);

FSeek(Header.Table2_Offset + 0x28);
if (Header.Table2_FileCount > 0)
    PACK_FileTable Table2(Header.Table2_FileCount);

```


Data field of each entry should contain the full BXON for that entry, seems some PACKs contain some extra data that isn't handled by this though, not sure why that is yet, looks like it might be something to do with the UnkData_Offset field.
Maybe that data is pointed at by the BXON themselves, similar to the info.arc BXON pointing to offsets in other arc files? (my guess is maybe this is data shared by multiple files in the PACK?)

E2: If anyone wants to dig in the game EXE for any info, it seems the EXE uses hashes instead of struct names, eg. EXE has no mentions of "tpXonAssetHeader" anywhere, but the bytes nearby (that I guess are a hash) "F0 29 FB 38" do have a mention in there.

E3: also made 010 editor template for parsing decompressed info.arc, thanks to LinkOFF & DKDave's info:

```
{
    local long header_pos = FTell();

    DWORD Magic;
    DWORD Version; // 3 in Nier, 1 in DQXIS

    DWORD StructNameHash;
    DWORD StructNameOffset;
    DWORD StructDataOffset;

    FSeek(header_pos + 0xC + StructNameOffset);
    string StructName;
};

enum<BYTE> CompressionType
{
    Solid = 0,
    SeperateBlobs1 = 1,
    SeperateBlobs2 = 2, // dunno what difference is
};

typedef struct
{
    local long archive_pos = FTell();

    DWORD NameOffset;
    DWORD Unk4; // always 4?
    CompressionType Flags;

    // pad bytes always set to 0x40?
    BYTE Pad9;
    BYTE PadA;
    BYTE PadB;

    local long archive_end_pos = FTell();

    FSeek(archive_pos + 0 + NameOffset);
    string Name;

    FSeek(archive_end_pos);
} BXON_tpArchiveFileParam_Archive<read=ReadBXON_tpArchiveFileParam_Archive>;

typedef struct
{
    local long file_pos = FTell();

    DWORD Unk0;
    DWORD NameOffset;
    DWORD FileOffset<read=ReadFileOffset>; // offset needs to be multiplied by 0x10 always!

    DWORD CompressedLength;
    DWORD UncompressedHeadersLength; // size of PACK headers/data
    DWORD UncompressedDataLength; // seems to be the size of UnkData part of PACK?

    BYTE ArchiveIdx;
    BYTE Flags;

    // pad bytes always set to 0x40?
    BYTE Pad1A;
    BYTE Pad1B;

    local long file_end_pos = FTell();

    FSeek(file_pos + 0x4 + NameOffset);
    string Name;

    FSeek(file_end_pos);
} BXON_tpArchiveFileParam_File<read=ReadBXON_tpArchiveFileParam_File>;

// multiplies offset by 0x10 for template window view
string ReadFileOffset(DWORD offset)
{
    local uint64 offs = offset;
    offs = offs * 0x10;
    string s;
    SPrintf(s, "%Lu", offs);
    return s;
}

string ReadBXON_tpArchiveFileParam_Archive(BXON_tpArchiveFileParam_Archive& entry)
{
    return entry.Name;
}

string ReadBXON_tpArchiveFileParam_File(BXON_tpArchiveFileParam_File& entry)
{
    string s;
    SPrintf(s, "%s:/%s", Archive.Archives[entry.ArchiveIdx].Name, entry.Name);
    return s;
}

// Seperate struct so files can be collapsed in template window...
struct BXON_tpArchiveFileParam_FileTable(int FileCount)
{
    BXON_tpArchiveFileParam_File Files[FileCount] <optimize=false>;
};

struct BXON_tpArchiveFileParam
{
    local long archive_param_pos = FTell();

    DWORD ArchiveCount;
    DWORD ArchiveTableOffset;
    DWORD FileCount;
    DWORD FileTableOffset;

    FSeek(archive_param_pos + 0x4 + ArchiveTableOffset);
    BXON_tpArchiveFileParam_Archive Archives[ArchiveCount] <optimize=false>;

    FSeek(archive_param_pos + 0xC + FileTableOffset);
    BXON_tpArchiveFileParam_FileTable Files(FileCount);
};

local long pos = FTell();

BXON_Header Header;

if(Header.StructName == "tpArchiveFileParam")
{
    FSeek(pos + 0x10 + Header.StructDataOffset);
    BXON_tpArchiveFileParam Archive;
}

```
## Post #13
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-04-26T12:44:52+00:00
- Post Title: NieR Replicant ver.1.22 .arc

[https://github.com/yretenai/kaine](https://github.com/yretenai/kaine)
## Post #14
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2021-04-26T15:25:37+00:00
- Post Title: NieR Replicant ver.1.22 .arc

Unpacker - [https://disk.yandex.ru/d/TqBu-IUq7Ku88Q](https://disk.yandex.ru/d/TqBu-IUq7Ku88Q)
Drag&drop info.arc
## Post #15
- Username: DaniKH
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Oct 11, 2018 5:15 am
- Post datetime: 2021-04-27T06:49:58+00:00
- Post Title: NieR Replicant ver.1.22 .arc

> Reply from Ekey ↑Mon Apr 26, 2021 8:44 pm at Mon Apr 26, 2021 8:44 pm
>
> 
https://github.com/yretenai/kaine

That's great! Works perfectly fine! Any idea about when the meshes can be exportable?
## Post #16
- Username: vvampii
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 12, 2019 12:37 pm
- Post datetime: 2021-04-27T07:04:11+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

> Reply from DaniZaya ↑Tue Apr 27, 2021 2:49 pm at Tue Apr 27, 2021 2:49 pm
>
> 
Ekey wrote: ↑Mon Apr 26, 2021 8:44 pm
https://github.com/yretenai/kaine


That's great! Works perfectly fine! Any idea about when the meshes can be exportable?

from discord server - its being worked on at the moment
## Post #17
- Username: WoefulWolf
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 16, 2020 4:01 pm
- Post datetime: 2021-04-27T10:34:29+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

> Reply from DaniZaya ↑Tue Apr 27, 2021 2:49 pm at Tue Apr 27, 2021 2:49 pm
>
> 
Ekey wrote: ↑Mon Apr 26, 2021 8:44 pm
https://github.com/yretenai/kaine


That's great! Works perfectly fine! Any idea about when the meshes can be exportable?

Currently working on reversing meshes, but fresh eyes can always help! Here's the templates we've been working on:
[https://github.com/WoefulWolf/replicant ... templates/](https://github.com/WoefulWolf/replicant_tools/blob/main/binary_templates/)
and like rotteneyed mentioned, we work from the NieR:Modding Discord server.
## Post #18
- Username: DaniKH
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Oct 11, 2018 5:15 am
- Post datetime: 2021-04-27T13:20:41+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

Currently working on reversing meshes, but fresh eyes can always help! Here's the templates we've been working on:
[https://github.com/WoefulWolf/replicant ... templates/](https://github.com/WoefulWolf/replicant_tools/blob/main/binary_templates/)
and like rotteneyed mentioned, we work from the NieR:Modding Discord server.
[/quote]

Wheres that Discord Server?? Im iterested
## Post #19
- Username: WoefulWolf
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 16, 2020 4:01 pm
- Post datetime: 2021-04-27T13:34:34+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

> Reply from DaniZaya ↑Tue Apr 27, 2021 9:20 pm at Tue Apr 27, 2021 9:20 pm
>
> 
Wheres that Discord Server?? Im iterested

I hope Discord server invite links aren't against the rules: [https://discord.gg/QBZZZvTeRa](https://discord.gg/QBZZZvTeRa)
## Post #20
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2021-04-27T14:05:32+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

My updated suggestion about table in info.arc:
4 - unknown (grow up with each cycle)
4 - name offset
4 - offset*16
4 - compressed chunk length
4 - uncompressed length
4 - if > 0 uncompressed data length, previuos value is PACK header length (with all information besides data)
1 - arc index (0 - lang1.arc, 1 - lang2.arc, 2 - common.arc, 3 - param.arc, 4 - init.arc, 5 - stream.arc)
1 - flag (compression 0 or 1; common.arc compressed exactly like info.arc and always have flag 0)
2 - padding (40 40)

Anyone have any idea what the first value is?
## Post #21
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2021-04-27T19:18:17+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

Something interesting, game seems to try loading a non-existent "directory.arc" file, the same code that loads info.arc (@ 1408EBAE0) also tries loading that too, wonder if it might be something for loading loose files outside of the main arcs.

Seems they use similar code for reading it as BXON like info.arc - in info.arc's case it checks for 0x276C7934 ID (probably hash of 'tpArchiveFileParam'), while directory.arc is looking for 0x1B7BB062, no idea what struct name that's meant to be though.

Procmon also shows it trying to load some loose bnk files too, I guess maybe movies could be replaced without needing repack, didn't see anything like it for sound files though sadly.

E:

> Reply from LinkOFF ↑Tue Apr 27, 2021 10:05 pm at Tue Apr 27, 2021 10:05 pm
>
> 
My updated suggestion about table in info.arc:
4 - unknown (grow up with each cycle)

Anyone have any idea what the first value is?

My guess is hash, you can compare the value of that in entries with very similar filenames (eg. the first mot_dyw010/mot_dyw011 entries, or msh_spl_visivle003_1, msh_spl_visivle003_2, msh_spl_visivle003_3) the unknown value only increases by 1 on each, but it's much different when entry names aren't similar, maybe gives a clue about the hasher they use.

E2: actually, you were right about the value increasing with every entry too, eg. the last entry has something like 0xFFFF85E2 as the value. Very strange, really can't explain that stuff about similar names still only increasing by 1. Maybe will need to look into info.arc loading code (nasty stuff tho ;_;)
## Post #22
- Username: rhadamants
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 10, 2014 3:13 am
- Post datetime: 2021-04-27T19:56:57+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

Has anyone figured out which file the game texts are in?

I extract all the files using the emil.exe tool, but I have not found anything like Lang, Language, Localization, etc.

The lang_en directory has 1kb files.
## Post #23
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2021-04-27T20:14:39+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

> Reply from rhadamants ↑Wed Apr 28, 2021 3:56 am at Wed Apr 28, 2021 3:56 am
>
> 
Has anyone figured out which file the game texts are in?

I extract all the files using the emil.exe tool, but I have not found anything like Lang, Language, Localization, etc.

The lang_en directory has 1kb files.
param\snow\text if you use my tool on previous page.
## Post #24
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2021-04-27T21:03:12+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

> Reply from infogram ↑Wed Apr 28, 2021 3:18 am at Wed Apr 28, 2021 3:18 am
>
> 
My guess is hash, you can compare the value of that in entries with very similar filenames (eg. the first mot_dyw010/mot_dyw011 entries, or msh_spl_visivle003_1, msh_spl_visivle003_2, msh_spl_visivle003_3) the unknown value only increases by 1 on each, but it's much different when entry names aren't similar, maybe gives a clue about the hasher they use.
I tried to reimport modified data but game wont start if compressed chunk changes even by one byte (i added it to lang1.arc). But It works with original compressed chunks. I tried to rewrite offset and size in info.arc.
## Post #25
- Username: rhadamants
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 10, 2014 3:13 am
- Post datetime: 2021-04-28T04:19:09+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

> Reply from LinkOFF ↑Wed Apr 28, 2021 4:14 am at Wed Apr 28, 2021 4:14 am
>
> 
rhadamants wrote: ↑Wed Apr 28, 2021 3:56 am
Has anyone figured out which file the game texts are in?

I extract all the files using the emil.exe tool, but I have not found anything like Lang, Language, Localization, etc.

The lang_en directory has 1kb files.

param\snow\text if you use my tool on previous page.

It's appear to be in the same format as the PS3 version.
Is there any parse for these texts?
## Post #26
- Username: lehieugch68
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 09, 2019 7:09 pm
- Post datetime: 2021-04-28T19:33:23+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

> Reply from rhadamants ↑Wed Apr 28, 2021 12:19 pm at Wed Apr 28, 2021 12:19 pm
>
> 
It's appear to be in the same format as the PS3 version.
Is there any parse for these texts?

Can you upload a sample file?
## Post #27
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2021-04-29T12:31:54+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

Petra on the discord found a way to load up loose files without needing to repack to arc, maybe pointless to repost since anyone interested is probably on there already, but is always good to keep info stored somewhere searchable outside of discord though:

> Loading (pseudo) loose files for NieR Replicant ver.1.22474487139
>
> 
>
> Requirement:
>
> https://github.com/yretenai/kaine/releases (emil.exe specifically)
>
> 
>
> -Extract all .arc files using emil.exe to a temp destination of your choice.  You should end up with a folder that contains 15 folders and a single .bxon file. (maybe more if you unpack DLC)
>
> 
>
> -Copy the contents of \steamapps\common\NieR Replicant ver.1.22474487139\data\sound   TO   <<your temp extracted path>>\sound
>
> 
>
> -Remove the .xap file extension for all extracted files.  Do not do what I did and do each one-by-one manually.
>
> 
>
> Batch remove all .xap file extensions
>
> 
>
> -Windows command prompt in the folder that contains the 15 folders you extracted and run the following command and grab lunch/coffee/whatever.  Will take a good 20-30 min.  Maybe @Yretenai can add a flag to ignore file extensions on export if the idea pans out?
>
> 
>
> forfiles /S /M *.xap /C "cmd /c rename @file @fname"
>
> 
>
> -Create the following folder structure on the same drive Nier Replicant is installed:
>
> 
>
> <<Steam Install>>
>
> -steamapps
>
>   -common
>
>     -build_assets
>
>       -rom
>
>         -pc
>
> 
>
> -Copy/Paste/Cut the 15 folder and single .bxon folder into the pc folder created above
>
> 
>
> -Rename your current \steamapps\common\NieR Replicant ver.1.22474487139\data folder to anything other than data
>
> 
>
> -Launch the game via Steam as per usual.
>
> 
>
> YMMV, but my experience has been no different playing this way thus far.
>
> 
>
> Edit 1:  Currently getting a black screen in intro and cut-scenes.  Likely a missed or additional export/extract and will look into tomorrow.  Audio files needed some additional work so these needing that as well would not be surprising.
>
> 
>
> Edit 2:  Confirmed \data\movie\*.arc did not extract . 
>
> Workaround - copy contents of  NieR Replicant ver.1.22474487139\data\movie TO \steamapps\common\build_assets\rom\pc\movie

Sounds like game checks for "..\build_assets\rom\pc\" folder, if it exists then it'll load files from there instead of from *.arc.
Would be nice if there was a way to let the game load *.arc but override with loose files if they exist, so full arc extracting wouldn't be needed. I've done something like that with UE4 on the past, probably no chance I could figure that with this Denuvo-mess of an EXE though 

Maybe it'd be interesting to see if load times change at all with this?
## Post #28
- Username: rhadamants
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 10, 2014 3:13 am
- Post datetime: 2021-05-02T15:38:07+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

> Reply from lehieugch68 ↑Thu Apr 29, 2021 3:33 am at Thu Apr 29, 2021 3:33 am
>
> 
rhadamants wrote: ↑Wed Apr 28, 2021 12:19 pm
It's appear to be in the same format as the PS3 version.
Is there any parse for these texts?


Can you upload a sample file?
[Nier_Replicant_BLJM60223.rar](https://www57.zippyshare.com/v/zZ3xzD5z/file.html)
## Post #29
- Username: lehieugch68
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 09, 2019 7:09 pm
- Post datetime: 2021-05-03T01:39:21+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

> Reply from rhadamants ↑Sun May 02, 2021 11:38 pm at Sun May 02, 2021 11:38 pm
>
> 
lehieugch68 wrote: ↑Thu Apr 29, 2021 3:33 am
rhadamants wrote: ↑Wed Apr 28, 2021 12:19 pm
It's appear to be in the same format as the PS3 version.
Is there any parse for these texts?


Can you upload a sample file?

Nier_Replicant_BLJM60223.rar

If I'm not mistaken, are these tab-delimited values (0x09) plain text files?
## Post #30
- Username: rhadamants
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 10, 2014 3:13 am
- Post datetime: 2021-05-03T03:15:38+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

> Reply from lehieugch68 ↑Thu Apr 29, 2021 3:33 am at Thu Apr 29, 2021 3:33 am
>
> 

If I'm not mistaken, are these tab-delimited (0x09) plain text files?

It's ps3 jpn and en patch files.
## Post #31
- Username: lehieugch68
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 09, 2019 7:09 pm
- Post datetime: 2021-05-03T08:46:16+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

> Reply from rhadamants ↑Mon May 03, 2021 11:15 am at Mon May 03, 2021 11:15 am
>
> 

It's ps3 jpn and en patch files.

When I extract the NieR v1.22 localization files, I found them to be just plain text files containing tab-delimited values (almost like TSV). Have you tried to modify and reimport them to the original file?

I attach a sample file here.
[talk_A.en.zip](https://xentaxbackup.github.io/file/20029_talk_A.en.zip)
## Post #32
- Username: hammo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 24, 2022 3:56 pm
- Post datetime: 2022-12-05T08:41:09+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

> Reply from Ekey ↑Mon Apr 26, 2021 8:44 pm at Mon Apr 26, 2021 8:44 pm
>
> 
https://github.com/yretenai/kainebackrooms game
thanks, i face some issue and this link provides me the answer!
## Post #33
- Username: samThunderbang
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 16, 2022 12:02 pm
- Post datetime: 2022-12-16T04:06:45+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

Does anyone actually know how to use the extractor!? 
I been trying to install the Father NieR subtitles and I am getting awfully frustrated because it doesn't tell you how to use it nor install all the things you need to extract the .arc files.
So can someone please give me a guide to follow so I could Install the mod successfully?
## Post #34
- Username: yarrmateys
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 20, 2012 9:41 am
- Post datetime: 2023-01-16T11:19:58+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

> Reply from samThunderbang ↑Fri Dec 16, 2022 12:06 pm at Fri Dec 16, 2022 12:06 pm
>
> 
Does anyone actually know how to use the extractor!? 
I been trying to install the Father NieR subtitles and I am getting awfully frustrated because it doesn't tell you how to use it nor install all the things you need to extract the .arc files.
So can someone please give me a guide to follow so I could Install the mod successfully?
i had the same problem, but turns out the best place to put a list of arguments is not the readme (only the program title goes there after all), nor a mention when running program without any commands, but on the releases page. type emil --help
## Post #35
- Username: alfur
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 16, 2023 5:18 pm
- Post datetime: 2023-03-07T16:17:17+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

Hey, i'm trying to unpack the arc files from nier replicant, but emil.exe keeps closing as i open it, can you help me please ?
## Post #36
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-03-07T20:55:58+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

> Reply from alfur ↑Wed Mar 08, 2023 12:17 am at Wed Mar 08, 2023 12:17 am
>
> 
Hey, i'm trying to unpack the arc files from nier replicant, but emil.exe keeps closing as i open it, can you help me please ?

this is command line tool so you need to run it with proper parameters [https://www.google.com/search?client=fi ... ne+program](https://www.google.com/search?client=firefox-b-d&q=how+to+run+command+line+program)

btw, here is download link for the ones who are looking for it [https://github.com/yretenai/kaine/releases](https://github.com/yretenai/kaine/releases)
## Post #37
- Username: alfur
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 16, 2023 5:18 pm
- Post datetime: 2023-03-08T07:23:05+00:00
- Post Title: Re: NieR Replicant ver.1.22 .arc

> Reply from ikskoks ↑Wed Mar 08, 2023 4:55 am at Wed Mar 08, 2023 4:55 am
>
> 
this is command line tool so you need to run it with proper parameters https://www.google.com/search?client=fi ... ne+program

btw, here is download link for the ones who are looking for it https://github.com/yretenai/kaine/releases

it keeps closing immediately  [https://drive.google.com/file/d/188eNLL ... sp=sharing](https://drive.google.com/file/d/188eNLLQpM_RdyXb5c2NdraJ6UctGhXJr/view?usp=sharing)
