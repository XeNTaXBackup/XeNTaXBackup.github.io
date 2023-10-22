## Post #1
- Username: TheGmodNugget
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 13, 2017 4:29 am
- Post datetime: 2021-02-12T02:39:51+00:00
- Post Title: The Da Vinci Code - PAK files

I need some help with figuring out how to get these paks decompiled. It runs off of the same engine as Indiana Jones and the Emperor's Tombs. Any help would be appreciated.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-12T08:48:56+00:00
- Post Title: The Da Vinci Code - PAK files

Can you upload some samples?
## Post #3
- Username: TheGmodNugget
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 13, 2017 4:29 am
- Post datetime: 2021-02-13T00:18:47+00:00
- Post Title: The Da Vinci Code - PAK files

This is the first time I've used dropbox so hopefully, I did it correctly. The zip just has 3 paks for one mission. 

(EDIT: Link did not work! fixed it!)
[https://www.dropbox.com/s/vnm1pa52mlba9 ... e.zip?dl=0](https://www.dropbox.com/s/vnm1pa52mlba9p1/res_m0x_louvre.zip?dl=0)
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-15T23:18:02+00:00
- Post Title: The Da Vinci Code - PAK files

I was able to partially figure out this file format and here is the documentation
[http://wiki.xentax.com/index.php/Slayer_Engine_PAK](http://wiki.xentax.com/index.php/Slayer_Engine_PAK)

It seems that it is very similar to PAK file from Buffy the Vampire Slayer,
but there are some differences and that's why quickbms script for Buffy doesn't work.
So currently there is no tool to support PAK format from The Da Vinci Code.
## Post #5
- Username: TheGmodNugget
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 13, 2017 4:29 am
- Post datetime: 2021-02-16T01:03:06+00:00
- Post Title: The Da Vinci Code - PAK files

Is there anyone around who may have a better handle on how to crack it? I don't know if the QBMS guy is still making scripts or if he'd be willing to do it.
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-16T08:42:29+00:00
- Post Title: The Da Vinci Code - PAK files

> Is there anyone around who may have a better handle on how to crack it?
I don't know.
## Post #7
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-06-13T11:58:14+00:00
- Post Title: The Da Vinci Code - PAK files

Sorry to update an old thread but I had a look at this and have come up with the below. It's not perfect and still has a lot of unknowns but is enough to extract most assets from these archives. This structure is just for the main pak files, not the segment (_seg%02d.pak) ones. 

```
{
   Header header;
   PakHeader pakHeader;
   
   TArray<int> StringOffsets;
   char StringTable[pakHeader.StringTableSize];
   
   int ResourceMinStringOffsetIndex;
   int ResourceFileDataInfoCount; // total number of ResourceFileDataInfo
   TArray<ResourceFolder> ResourceFolders;
   ResourceType ResourceTypes[x]; // read until TypeId == -1
   
   FileInfo StreamedFiles[header.StreamedFileCount];
   FileInfo CommonFiles[34];
   
   char Padding[x]; // to header.UnknownBlockOffset if != 0
   char UnknownBlock[header.UnknownBlockSize];
   
   FileInfo InlineFiles[x]; // read to end of file
}

typedef TString : TArray<char>;

struct TArray<T>
{
   int Length;
   T Items[Length];
}

struct Header
{
   uint Version;
   int Unknown04;
   int IsSegemented; // boolean
   int StreamedFileCount;
   int Unknown10;    // UnknownBlock file count maybe?
   int UnknownBlockOffset;
   int UnknownBlockSize;
}

struct PakHeader
{
   int StringTableSize;
   int Unknown04;
   int StringTableSize_2;
   int Unknown0C;
}

struct ResourceFolder
{
   char Data[38]; // char folder_name[36] + flags?
}

struct ResourceType
{
   int TypeId;
   TString Name;
   int Unknown08;
   TArray<TString> DirectoryNames;
   int Unknown10;
   TArray<ResourceFileInfo> ResourceFileInfos;
}

struct ResourceFileInfo
{
   ushort Index;
   ushort Unknown02;
   ushort StringOffsetIndex;
   TArray<ResourceFileDataInfo> FileDataInfos;
}

struct ResourceFileDataInfo
{
   ushort Unknown00;
   ushort StringOffsetIndex;
   int FileSize;
}

struct FileInfo
{
   int Unknown00;    // boolean
   int Offset;       // absolute offset to start of struct
   int Size;         // including Data
   int FileSize;     // can be 0 but still have Data!
   int Unknown10;    // boolean
   TString FileName;
   int Unknown18;    // boolean
   int IsStreamed;   // boolean. if true, Data is in a segment file not below
   int ResourceTypeId;
   int SegmentFileIndex;
   int Unknown28;
   int Unknown2C;   
   char Data[x];
}

```


Just some notes on this:
 - TArray is a length prefixed array. TString is the char variant of this
 - ResourceFolder is only named this as it appears to contains all sub folder names from all file paths
 - ResourceType is basically a binary representation of Resource_PC.cfg plus file info
 - StreamedFiles contains all files that are streamed (see below)
 - CommonFiles always has the same 34 files in all archives
 - UnknownBlock I couldn't figure out. It contains structured (mesh?) file data up to a point but changes halfway through
 - InlineFiles contains all files that have inline-data

As for the segment files, these are used to store file data for the streamed files which are streamed as-and-when needed. I couldn't see any offsets for the segments, instead it looks like the "StringOffsetIndex" maps to a file identifier (StringOffsetIndex -> StringOffsets -> StringTable) which is the first field in the segment data. These segment files have their own structure (which I've not looked into), but file data always starts at 0x800 and uses the following structure, so should be simple enough to parse - there is another unknown block of data at the end of these too though.

```
int Unknown
int TotalSize // from start of struct + padding
char Data[x]

```


C# code for reading is [here](https://gist.github.com/barncastle/60572ffa142322429c1fcc2a755d087d), I've not written a tool/code for extraction though.
