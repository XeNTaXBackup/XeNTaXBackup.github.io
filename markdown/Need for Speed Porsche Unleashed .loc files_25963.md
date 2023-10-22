## Post #1
- Username: bugsimtasdesimt
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 02, 2022 11:02 pm
- Post datetime: 2022-11-03T14:01:05+00:00
- Post Title: Need for Speed Porsche Unleashed .loc files

I want to edit the .loc files in nfs porsche unleashed, are there any existing tools for it?
Its an EA Canada game and I found out its the same format as SSX Tricky.
I can edit the strings by adding spaces in letters I don't use, but I cannot edit string length.
[festrings.zip](https://xentaxbackup.github.io/file/22995_festrings.zip)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2022-11-13T21:14:56+00:00
- Post Title: Need for Speed Porsche Unleashed .loc files

File format uses offsets, so editing string length requires those editing too

Rough format

```
//--- 010 Editor v13.0 Binary Template
//
//      File: 
//   Authors: 
//   Version: 
//   Purpose: 
//  Category: 
// File Mask: festrings.loc
//  ID Bytes: 
//   History: 
//------------------------------------------------

struct ParseHeader
{
  uint one; Assert(one==1);
  uint count;
  uint offsets[count]; // absolute from file start
};

struct IndexPair
{
  ushort val;
  ushort index;
};

struct ParseIndices
{
  uint count;
  uint zero; Assert(zero==0);
  IndexPair pairs[count];
};

struct ParseInfo
{
  uint zero; Assert(zero==0);
  uint size;
  uint offsets[size]; // relative to struct
};

struct Section
{
    char sig[4];
    uint size;

    union {
        switch(sig) {
            case "LOCH": ParseHeader hdr; break;
            case "LOCI": ParseIndices idc; break;
            case "LOCL": ParseInfo nfo; break;
            default : Assert(false, "unhandled");
        }
        
        ubyte data[size-8];
    } u;
 
};

while(FTell() < FileSize()) {
    Section s;
}

```
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-13T21:26:55+00:00
- Post Title: Need for Speed Porsche Unleashed .loc files

Some other EA games also use this format [http://wiki.xentax.com/index.php/EA_Games_LOC](http://wiki.xentax.com/index.php/EA_Games_LOC)
