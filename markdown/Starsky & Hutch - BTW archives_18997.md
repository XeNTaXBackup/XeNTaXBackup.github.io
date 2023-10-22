## Post #1
- Username: grandsonpyrodrone
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 31, 2018 4:50 am
- Post datetime: 2018-10-30T21:05:09+00:00
- Post Title: Starsky & Hutch - BTW archives

Ok so, I'm trying to open some .btW files from the PC version of Starsky & Hutch, To get some car models and their textures, Though I don't know how. Could anyone try to help? [https://www.dropbox.com/s/nedtmuqui32md ... n.btW?dl=0](https://www.dropbox.com/s/nedtmuqui32md8r/Common.btW?dl=0) [https://www.dropbox.com/s/3sqfx2mvvg72s ... x.btw?dl=0](https://www.dropbox.com/s/3sqfx2mvvg72s5k/HiResTex.btw?dl=0) [https://www.dropbox.com/s/2ci9ypa0f7t5i ... x.btw?dl=0](https://www.dropbox.com/s/2ci9ypa0f7t5ik1/LoResTex.btw?dl=0)
## Post #2
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-11-13T14:52:49+00:00
- Post Title: Starsky & Hutch - BTW archives

Sorry to bump an old thread, but has anyone tried to reverse engineer Starsky & Hutch .btw archives?
## Post #3
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-11-13T19:20:26+00:00
- Post Title: Starsky & Hutch - BTW archives

[https://drive.google.com/file/d/1UpV4mB ... sp=sharing](https://drive.google.com/file/d/1UpV4mB1pD2BK99vkt4pKgBCJIQeQahNz/view?usp=sharing)
[https://drive.google.com/file/d/1MQFuPB ... sp=sharing](https://drive.google.com/file/d/1MQFuPBP6BlNn0ZDJ3PdoNVU1Kqwb3zlI/view?usp=sharing)

If someone should come across, it would be great to reverse engineer here.
## Post #4
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2021-11-14T15:34:06+00:00
- Post Title: Starsky & Hutch - BTW archives

the format for the geometry looks to be pretty straight forward, I'm not even sure if this file you uploaded even has textures, I first though it could have some dxt texture but nah, maybe if its swizzled, but I don't think so.
## Post #5
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-12-05T20:52:09+00:00
- Post Title: Starsky & Hutch - BTW archives

Is there a tool to unpack S&H .btW files with known filenames?
## Post #6
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-06-24T16:23:55+00:00
- Post Title: Starsky & Hutch - BTW archives

Sorry for updating an old thread but I've documented the file format for this game. 

```
{
  Header header;
  Offsets offsets;  
  
  byte Data[x];  
  
  FileNameInfo fileNameInfos[offsets.FileNameCount];
  FileDataInfo fileDataInfos[offsets.FileDataInfoCount];  
  PackedName packedNames[offsets.PackedNameCount];  
  char extensionNames[offsets.ExtensionNameCount][4]; // null padded to 4 chars
  PackedName packedNumberedNames[offsets.PackedNumberedNameCount];
  char stringTable[offsets.StringTableSize];
}

struct Header
{
  int Unknown00;
  int Unknown04;
  char Magic[4]; // "WAD!"
  int Version;
  byte Unknown10[8];
  char Description[128];
}

struct Offsets
{
  int DataOffset;
  int DataSize;
  int FileNameCount;
  int FileNameOffset;
  int FileNamePtr;
  int FileDataInfoCount;
  int FileDataInfoOffset;
  int PackedNameCount;
  int PackedNameOffset;
  ushort NameDelta;
  ushort FileDelta;
  int ExtensionNameOffset;
  int ExtensionNameCount;
  int PackedNumberedNameOffset;
  int PackedNumberedNameCount;
  int StringTableOffset;
  int StringTableSize;
}

struct FileNameInfo
{
  ushort DirNameCount;
  ushort DirNameOffset;
  ushort FileNameCount;
  ushort FileNameOffset;
}

struct FileDataInfo
{
  int Size;
  int Offset;
}

struct PackedName
{
  // 0x7F        = no extension i.e. folder
  // 0x7E        = invalid extension
  // 0x79 - 0x7D = ordinal string of (0x7E - n) length
  // 0x77 - 0x78 = ordinal string with separator
  // else        = extension index
  int ExtIndex : 7
  int NameLength : 8
  int NameIndex : 17
}

```


The structure itself is pretty straight forward however unpacking filepaths requires some specific logic.

String information is packed in a structure I called "PackedName". For most files this is simply, "read StringTable from NameIndex, for NameLength characters, and append ExtensionName at ExtIndex", however ExtIndex values of ≥ 0x77 are special codes requiring custom logic. These codes are mainly used for files that contain ordinals and therefore share common base names e.g. Test_#.png => Test_01.png, Test_02.png etc. Instead of storing each filename, a template "base" string ("Test_#.png") is stored in PackedNumberedNames and only the ordinal ("01", "02", ...) part is stored in the name - providing deduplication at both levels, with the "base" string being referenced by NameIndex and stitched together. You can see my implementation for this [here](https://gist.github.com/barncastle/1bd317ed7ac30ae01528485c0d2291e2#file-starskyhutchbtw-cs-L107).

Additionally, each packed string only represents a fragment of a file path, usually either a file or folder name. Recursive logic using the FileNameInfo structs is used to combine all of the path parts together correctly. There are a few quirks with this but hopefully my [implementation ](https://gist.github.com/barncastle/1bd317ed7ac30ae01528485c0d2291e2#file-starskyhutchbtw-cs-L63) is clear enough to demonstrate this.

My full C# implementation and a tool is available [here](https://gist.github.com/barncastle/1bd317ed7ac30ae01528485c0d2291e2). Place the extractor in the game's directory, run and it'll extract all the assets to a new folder called "Dump".
