## Post #1
- Username: asasfdfsfs
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 12, 2014 5:02 am
- Post datetime: 2016-08-13T22:54:21+00:00
- Post Title: No Man's Sky Language Files (.mbin)

Hello. No Man's Sky language files how to the unpack/pack .mbin?

Example : [https://yadi.sk/d/bTKnPP9GuCJGH](https://yadi.sk/d/bTKnPP9GuCJGH)
## Post #2
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2016-08-14T13:25:25+00:00
- Post Title: No Man's Sky Language Files (.mbin)

Text block offset: 0x26D070
## Post #3
- Username: atvaark
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Aug 28, 2015 10:19 pm
- Post datetime: 2016-08-14T13:51:28+00:00
- Post Title: No Man's Sky Language Files (.mbin)

> Reply from asasfdfsfs
>
> Hello. No Man's Sky language files how to the unpack/pack .mbin?

Example : https://yadi.sk/d/bTKnPP9GuCJGH

```
//--- 010 Editor v7.0.2 Binary Template
//
//      File: NMS_MBIN.bt
//   Authors: Atvaark
//   Version: 1
//   Purpose: 
//  Category: 
// File Mask: 
//  ID Bytes: 
//   History: 
//------------------------------------------------

typedef struct {
  int32 cc;
  int32 version;
  int32 padding;
  int32 padding;
  int64 hash;
  char type[64];
  int64 padding;
} Header;

typedef struct {
  int32 offset;
  int32 padding;
  int32 length;
  uint32 unknown; // 01 AA AA AA

  if (length > 0) {
      local int64 end = FTell();
      FSeek(startof(this) + offset);
      char line[length];
      FSeek(end);
  }
} LocalisationLine <optimize=false>;

typedef struct(uint32 count) {  
  char key[32];
  LocalisationLine lines[count];
} LocalisationTableEntry <optimize=false>;

typedef struct {
  int32 lineCount;
  int32 padding;
  int32 entryCount;
  int32 unknown;  
} LocalisationTableHeader;

typedef struct {
  LocalisationTableHeader header;
  LocalisationTableEntry entries(header.lineCount)[header.entryCount];
} LocalisationTable;

Header header;

if (header.type != "cTkLocalisationTable") {
  Printf("Unknown archive");
  return;
}

LocalisationTable table;

```
## Post #4
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2016-08-15T21:54:47+00:00
- Post Title: No Man's Sky Language Files (.mbin)

Tool from swuforce - [https://yadi.sk/d/6etMaVJhuEwuS](https://yadi.sk/d/6etMaVJhuEwuS)
