## Post #1
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2006-10-16T12:47:32+00:00
- Post Title: Gothic 3 .pak extractor

Hi
Especially Mr. Mouse   

I would like to extract files from my Gothic 3 game, but I cannot open .pak file
Can anybody help me?
some .pak can be ound here:

```
http://rapidshare.de/files/36954338/Strings.pak.html
```


It is strings.pak:: 2.5MB

I looked at it in hex and it looks similiar to some archives I saw before, but I duno.
See attachment
[strings.JPG](https://xentaxbackup.github.io/file/928_strings.JPG)
## Post #2
- Username: john_doe
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2006-10-16T14:10:22+00:00
- Post Title: Gothic 3 .pak extractor

Already done 
[http://gamefileformats.the-underdogs.in ... orer10.zip](http://gamefileformats.the-underdogs.info/files/g3explorer10.zip)
The user interface is in German but it should work without knowing the language.

@MrMouse:
These are the specs, copied from another forum:

```
//
//  Gothic3 PAK file format specs.
//  (all values are little-endian)
//  Copyright (c) 2006 Nico Bendlin <nicode@gmx.net>
//
//  +----------------+
//  |  file header   |
//  +----------------+
//  |   file data    |
//  +----------------+
//  |    unknown     |
//  | (not present)  |
//  +----------------+
//  |   file table   |
//  +----------------+
//  |    unknown     |
//  | (empty string) |
//  +----------------+
//
////////////////////////////////////////////////////////////////////////////////

//
// Fix-sized file header
//
struct G3PakFileHeader {
    UInt32  Unknown0;   // Always 0x00000000. Might be part of the signature.
    UInt32  Signature;  // Always 0x30563347 ('G3V0').
    UInt64  Unknown1;   // Always 0x0000000000000000. Interpretation unknown.
    UInt64  Unknown2;   // Always 0x100067F800000001. Might be a UInt16[4] version (1.0.26616.16).
    UInt64  Unknown3;   // Always the same value as FileTable. Might be a file offset to an (currently) unused data block.
    UInt64  FileTable;  // File offset to the root entry of the file table.
    UInt64  Unknown4;   // File offset to an (currently) unused data block after the file table. Might be a comment string.
};

//
// String data (e.g. file names)
//
struct G3PakFileString {
    UInt32  Length;
    UInt8   Data[Length + 1];  // ANSI text. Only present if Length > 0. [Length] must be '\0'.
};

//
// File table entries (directories and files)
//
struct G3PakFileTableEntry {
    //
    // Fix-sized header for all entries
    //
    struct {
        UInt64  FileTime1;   // Windows FILETIME. Might be the CreationTime.
        UInt64  FileTime2;   // Windows FILETIME. Might be the LastAccessTime.
        UInt64  FileTime3;   // Windows FILETIME. Might be the LastWriteTime.
        UInt64  Unknown0;    // Always 0x0000000000000000. Interpretation unknown.
        UInt32  Attributes;  // Windows FILE_ATTRIBUTE_Xxx (other bits should be ignored).
    };
    //
    // Dynamically sized structures for directories and files
    //
    union {
        //
        // Directory entry (FILE_ATTRIBUTE_DIRECTORY in Attributes)
        //
        struct {
            G3PakFileString     FileName;     // String includes the relativ path to the root (path separator is '/') and ends with '/'.
            UInt32              DirCount;     // Count of directory entries that follow (directly after this count).
            G3PakFileTableEntry [DirCount];
            UInt32              FileCount;    // Count of file entries that follow (directly after this count).
            G3PakFileTableEntry [FileCount];
        };
        //
        // File entry (Attributes can include FILE_ATTRIBUTE_COMPRESSED)
        //
        struct {
            UInt64          Offset;    // File offset to raw data.
            UInt64          Bytes;     // Size of raw data in Bytes.
            UInt64          Size;      // Size of file data (uncompressed).
            UInt32          Unknown1;  // Always 0x00000000. Interpretation unknown.
            UInt32          Unknown2;  // 0x00000000 if uncompressed, 0x00000002 if compressed with ZLib (default compression level).
            G3PakFileString FileName;  // String includes the relativ path to the root (path separator is '/').
            G3PakFileString Comment;   // Includes the full native file name and path of the source file.
        };
    };
};
```
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-10-16T15:11:10+00:00
- Post Title: Gothic 3 .pak extractor

> Reply from john_doe
>
> Already done 
http://gamefileformats.the-underdogs.in ... orer10.zip
The user interface is in German but it should work without knowing the language.

@MrMouse:
These are the specs, copied from another forum:
nice man.
nice
what forum was it btw?
care to provide a link?
## Post #4
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2006-10-16T15:35:54+00:00
- Post Title: Gothic 3 .pak extractor

Thanks, it works....
## Post #5
- Username: john_doe
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2006-10-16T16:16:54+00:00
- Post Title: Gothic 3 .pak extractor

> Reply from lionheartuk
>
> what forum was it btw?
care to provide a link?

Here: [http://www.worldofgothic.de/foren/?go=index](http://www.worldofgothic.de/foren/?go=index)
It's in German, though.

I made the tool and NicoDE gave me his specs since I was missing some stuff (actually just the date/time fields )
## Post #6
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2006-10-20T20:20:44+00:00
- Post Title: Gothic 3 .pak extractor

And any tool for packing back the files?

I want to make a mod and I need to pack files back (or I should leave them in directory?)
## Post #7
- Username: john_doe
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2006-10-21T07:19:37+00:00
- Post Title: Gothic 3 .pak extractor

Yes, NicoDE made two command line tools, one for extracting and one for creating new archives.
You can get his tool from here: [http://forum.worldofplayers.de/forum/sh ... ost2487521](http://forum.worldofplayers.de/forum/showthread.php?p=2487521&#post2487521)
You need to be registered, though.
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-10-21T09:33:35+00:00
- Post Title: Gothic 3 .pak extractor

The .pak it's a normal zlib no?
## Post #9
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2006-10-21T13:35:31+00:00
- Post Title: Gothic 3 .pak extractor

Yes, it uses the normal zlib library.
## Post #10
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2006-10-21T17:57:19+00:00
- Post Title: Gothic 3 .pak extractor

Great, thanks............
