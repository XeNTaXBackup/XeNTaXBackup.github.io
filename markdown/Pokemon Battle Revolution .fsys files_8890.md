## Post #1
- Username: pkmnmstr
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 05, 2012 3:55 am
- Post datetime: 2012-05-04T20:05:03+00:00
- Post Title: Pokemon Battle Revolution *.fsys files?

Here are some sample files:
<EDIT: pm me for sample files>

EDIT: found this BMS script, but not sure if complete:

```
comtype lzss "12 4 2 2 0"

# 0x00
idstring "FSYS"
get TEMP long
get TEMP long
get DATA_COUNT long
# 0x10
get TEMP long
get TEMP long
get INFO_OFFSET long
get DATA_BASE long
# 0x20
get FILE_SIZE long

goto INFO_OFFSET
# 0x00
get OFFSET_ARRAY long
get NAME_TABLE   long
get BASE_OFFSET  long

For i = 0 < DATA_COUNT
   goto OFFSET_ARRAY
   get DATA_OFFSET long

   goto DATA_OFFSET
   # 0x00
   get DATA_HASH   long
   get OFFSET      long
   get SIZE        long
   get TEMP        long
   # 0x10
   get TEMP        long
   get ZSIZE       long
   get TEMP        long
   get TEMP        long
   # 0x20
   get TEMP        long
   get NAME_OFFSET long

   goto NAME_OFFSET
   get NAME string
   string NAME += ".fdat"

   goto OFFSET
   idstring "LZSS"
   get SIZE  long
   get ZSIZE long
   get DUMMY long
   savepos OFFSET
   math ZSIZE -= 12

   clog NAME OFFSET ZSIZE SIZE

   math OFFSET_ARRAY += 4
next i

```


I found this code snippet, but I'm not sure what language it is, or if it's just pseudocode, and how complete it is,
[spoiler]
```
* fsys.bt - Structure definitions for Pokemon Colosseum - fsys file related entities.
*
*****************************************************************************
* Revision History:
*  2009/09/29 - revel8n - Original
*  2010/02/22 - breakpoint - Initial changes from SSBM format
*  2010/02/22 - revel8n - minor updates
*  2010/02/24 - revel8n - updates to compensate for lack of script pointer type
*  2010/02/24 - revel8n - addition of initial jobj structure
*/

#include "common-types.bt"

local uint32 t, cnt, savedFilePointer;

void PushFP(void) { savedFilePointer = FTell(); }
void PopFP(void) { FSeek(savedFilePointer); }
// used only to provide a way of giving "empty" structures a perceived size
void PopOffsetFP(uint32 offset) {FSeek(savedFilePointer + offset);}

void FSeekOfs(uint32 ofs) { FSeek(sizeof(fileInfo.fileHeader) + ofs); }

// returns the number of consecutive 32-bit values until zero is reached
// zero itself is not included in the count, and file pointer is not moved
uint32 GetArrayCount(void)
{
    local uint32 cnt = 0;

    PushFP();
    while (ReadUInt(FTell()) != 0)
    {
        FSeek(FTell() + 4);
        cnt++;
    }
    PopFP();
    return cnt;
}

SetReadOnly(true);

// #pragma displayname("fsys structures")
// #pragma fileextensions(".fsys")

// #pragma byteorder(big_endian)
BigEndian();

// DAT_FILE File Structure
struct DAT_FILE
{
   // DAT_HEADER - DAT file header information structure
   SetBackColor(cLtGreen);
   struct DAT_HEADER
   {
        // small hack to determine difference between Pokemon .dat and SSBM .dat
        if (ReadUInt(0x00) == ReadUInt(0x40))
          uint32 unknown[16];     // unknown 0x40 (64) byte header information

      uint32 origDataSize  <format = hex>; // matches value at offset 0x00 and corresopnds with possibly being the original file/data size as it ends just after the string table if starting
        uint32 dataBlockSize <format = hex>;
        uint32 relocTableEntryCount;
      uint32 stringTableCount;
        uint32 unknown2[4];
   } fileHeader;

    SetBackColor(cLtRed);
    struct DATA_BLOCK
    {
        uint8 data[fileHeader.dataBlockSize];
    } dataBlock;

    SetBackColor(cLtBlue);
    struct RELOC_TABLE
    {
        uint32 relocOffset[fileHeader.relocTableEntryCount] <format = hex>;
    } relocTable;

    SetBackColor(cLtYellow);
   struct ROOT_NODE
   {
      uint32 dataOffset <format = hex>;
      uint32 nameOffset <format = hex>;
   } rootNode;

    SetBackColor(cLtAqua);
   struct
   {
      string nodeName;
   } stringTable[fileHeader.stringTableCount] <optimize = false>;
};

struct DAT_FILE fileInfo;
```
[/spoiler]

Why this game? Well it has the most models and probably best looking (around 500 + characters with bunch of customizations). Maybe the models are in some known format used by other games too, but if not, figuring out the archives is still a huge step.
## Post #2
- Username: RoxasKennedy
- Rank: beginner
- Number of posts: 21
- Joined date: Tue May 17, 2011 6:39 pm
- Post datetime: 2012-05-05T05:29:05+00:00
- Post Title: Pokemon Battle Revolution *.fsys files?

So far, the only way to get them is Dolphin Emulator and 3D Ripper DX. I haven't seen any way to get models from .fsys files yet.

Also, posting samples is now against the rules, so you might delete the link.
## Post #3
- Username: pkmnmstr
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 05, 2012 3:55 am
- Post datetime: 2012-05-05T09:25:23+00:00
- Post Title: Pokemon Battle Revolution *.fsys files?

> Reply from RoxasKennedy
>
> So far, the only way to get them is Dolphin Emulator and 3D Ripper DX. I haven't seen any way to get models from .fsys files yet.
I know that. I should have been more clear, sorry. However, if 3dripper was that great the forum admins could just close down the 3d section completely. It's not an alternative solution. And this topic is about fsys archive files, models is not the only thing we can be interested in.

> Also, posting samples is now against the rules, so you might delete the link.
Well then pm me for samples.

However that new rule will greatly decrease the productivity around here. To any mod reading this: have you guys actually contacted a legal counsellor about this? Usage of only part of a copyrighted material for purposes such as research is considered fair use and doesn't require the permission of the copyright holder.
Fair use or the similar term "fair dealing" exists in US, some commonwealth countries and some CIS countries (haven't looked up all of them) allow use of part of copyrighted material for reasons such as criticism, comment, news reporting, teaching, scholarship, and research in their acts dealing with intellectual property.
