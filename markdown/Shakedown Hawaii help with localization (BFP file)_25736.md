## Post #1
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2022-08-25T09:15:23+00:00
- Post Title: Shakedown: Hawaii help with localization (BFP file)

Someone knows how to deal with Shakedown Hawaii?
Wanted to add Italian translation...



[](https://ibb.co/2Zw7z2Y)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-25T19:39:27+00:00
- Post Title: Shakedown: Hawaii help with localization (BFP file)

Can you upload "gamedata.bfp" to mega.nz, google drive etc. and then share a public link here?
## Post #3
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2022-08-25T19:45:40+00:00
- Post Title: Shakedown: Hawaii help with localization (BFP file)

Here is it: [https://mega.nz/file/kj4WGZLB#kZYGHu3S2 ... jRKwr9lmbk](https://mega.nz/file/kj4WGZLB#kZYGHu3S2My7Xm1YK8h46-sFlvB3LFVkBjRKwr9lmbk)
## Post #4
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-08-26T00:58:25+00:00
- Post Title: Shakedown: Hawaii help with localization (BFP file)

ZLIB COMPRESSION.

Use offzip [https://aluigi.altervista.org/mytoolz/offzip.zip](https://aluigi.altervista.org/mytoolz/offzip.zip) to decompress.
## Post #5
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-08-27T15:08:51+00:00
- Post Title: Shakedown: Hawaii help with localization (BFP file)

I've documented the full format for this file below. As Rabatini said, most files are zlib compressed however not all.

The structure is pretty standard but has some quirks. After the header there are header.FileEntryCount "FileEntry" structs that contain a [name hash](https://gist.github.com/barncastle/435d49045962f75b2c6168dc89e191fe#file-shakedownhawaiibfp2-cs-L91), sizes and offset. This is followed by 0x100 "ScriptEntry" structs which are the same struct minus the name hash. Those are followed by a header.EagerLoadSegmentCount length int32 array (I've dubbed "eagerLoadSizes") then finally the data.

The game uses a lazy/eager file load mechanic that revolves around the LazyLoadByteCount and each entry's Offset and Size. If the Offset + CompressedSize is more than the current LazyLoadByteCount, a value is taken from the EagerLoadSizes array and a range is created. All files whose Offset falls within said range is eager loaded during the BFP2 file load - all other files are lazy loaded as-and-when required. Do note scripts are exempt from this mechanic and MUST be eager loaded. [Example here.](https://gist.github.com/barncastle/435d49045962f75b2c6168dc89e191fe#file-shakedownhawaiibfp2-cs-L80) 

Some notes:
 - Some of these script structs will be blank - the game only parses entries where the CompressedSize field is more than 0.
 - Scripts are loaded by index so order is important.
 - The TotalAlignedNamedDecompressedSize, TotalAlignedUnnamedDecompressedSize, AllDataDecompressedBufferSize and DecompressionBufferSize are all arbitrary values, the game doesn't validate them so, as long as they make sense and the buffer sizes large enough, one can set them to anything.
 - If CompressedSize != DecompressedSize, then the file is zlib compressed otherwise it is uncompressed.
 - [Names](https://gist.github.com/barncastle/435d49045962f75b2c6168dc89e191fe#file-shakedownhawaiibfp2-cs-L358) for certain files can be found in the binary. I've dumped all the easy to find ones.

C# implementation and tool can be found [here](https://gist.github.com/barncastle/435d49045962f75b2c6168dc89e191fe). Instructions on use at the end of the page.

```
{
    Header Header;
    FileEntry FileEntries[header.NamedEntryCount];
    ScriptEntry ScriptEntries[0x100];
    int EagerLoadSizes[header.EagerLoadSegmentCount];
    byte Data[x];
}

struct Header
{
    uint Magic; // "BFP2"
    int FileEntryCount;
    int TotalAlignedNamedDecompressedSize; // sum of "named" DecompressedSizes when 64 byte aligned
    int TotalAlignedUnnamedDecompressedSize; // sum of "unnamed" DecompressedSizes when 64 byte aligned
    int AllDataDecompressedBufferSize; // size of a buffer which stores all decompressed data
    int LazyLoadByteCount; // num of bytes to directly read, must include header + entries
    int FileDataSize; // length of file minus LazyLoadBytes
    int DecompressionBufferSize; // size of the zlib decompression buffer (largest 64 byte aligned CompressedSize)
    int EagerLoadSegmentCount;
    byte Padding[28];
}

struct FileEntry
{
    uint NameHash;
    int DataOffset;
    int DecompressedSize;
    int CompressedSize; // if compressed != decompressed, zlib else uncompressed
}

struct ScriptFileEntry
{
    int DataOffset;
    int DecompressedSize;
    int CompressedSize; // see above
}

```


EDIT: Have revisited this and fixed a bunch of errors.
## Post #6
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2022-08-28T12:45:25+00:00
- Post Title: Shakedown: Hawaii help with localization (BFP file)

WoW! Amazing work, thank you so much.

I just wanted to overwrite ENG with Italian language for an unofficial translation...
The text file seems to be [Dump\gametext.bxt](https://1drv.ms/u/s!ApMUGr0cuN39gplVevLaL-WE00qZIg?e=NXfFC6). How can I edit the strings and repack them in the working game?
## Post #7
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-08-31T15:10:36+00:00
- Post Title: Shakedown: Hawaii help with localization (BFP file)

Below is the BXT file structure. You'll notice that there are other languages included in these files but the game is hard-coded to only load the English entries.

```
  uint32 unknown00;
  uint32 unused;
  uint32 entryBaseOffset; // used to calculate locale offset, always entryOffsets[0] - 1
  uint32 entryOffsets[x];  
  StringEntry entries[x];
}

struct StringEntry {
   char english[]; // all null terminated
   char french[];
   char italian[];
   char german[];
   char spanish[];
}

```


---

Just to note I've gone over this format again and have corrected a bunch of mistakes and updated some unknown bits of information on my previous post. I've also updated the tool to be able to export and import files.
## Post #8
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2022-08-31T15:58:49+00:00
- Post Title: Shakedown: Hawaii help with localization (BFP file)

Great! Now all that is missing is a tool to edit the text strings in the .bxt files, automatically adjusting the new bytes length, null-terminations etc...

EDIT:
good news BTW, the game seems to correctly support foreign characters (in this example some Italian accented vowels):
[](https://ibb.co/ZJJ5Y11)
## Post #9
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2023-07-04T13:48:08+00:00
- Post Title: Shakedown: Hawaii help with localization (BFP file)

@barncastle
What about the bxt file with the strings? Can you write a small tool to generate a text file (UTF8) and reimport strings into the bxt? 
I'm not a coder unfortunately
## Post #10
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2023-07-05T16:27:58+00:00
- Post Title: Shakedown: Hawaii help with localization (BFP file)

Solved with a tool made by banz99 to Export editable XML file, and Re-Import XML into BXT files extracted with the tool above by barncastle.
The 3 files to extract for the strings are: gametext.bxt, objectives.bxt, records.bxt.

Tool attached: hope will help others to localize this game.

✌ Peace
[ShHawaii 1.0.zip](https://xentaxbackup.github.io/file/24022_ShHawaii 1.0.zip)
## Post #11
- Username: Korylon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 23, 2023 3:14 pm
- Post datetime: 2023-08-24T09:24:01+00:00
- Post Title: Shakedown: Hawaii help with localization (BFP file)

Thanks to the contribution from all of you, and seeing that Vblank seems to have no interest in translating these games currently, I want to share with you this translation into Spanish. For anyone who downloads it and finds any errors, please let me know so that we can get the best possible Spanish version 

[https://mega.nz/file/Xk1EVaqC#B9uQ8leCO ... 8N3_CoogUU](https://mega.nz/file/Xk1EVaqC#B9uQ8leCOhoqh_ujoq_dS9zlHS-QbXuEe8N3_CoogUU)

For those who don't understand much... unzip the .ZIP file and copy 'gamedata.bfp' to the root folder of the game.

P.S.: I appreciate the tools you created; without them, this wouldn't have been possible
