## Post #1
- Username: Druid8392
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 22, 2016 10:05 pm
- Post datetime: 2016-09-17T00:07:57+00:00
- Post Title: [Reqt] Impressions Games .ENG [Caesar/Emperor/Pharaoh/Zeus]

Anyone know how to extract Text from .ENG archive of Impressions Games

Caesar
Emperor
Pharaoh
Zeus

Preview of Archives
[https://dl.dropboxusercontent.com/u/153 ... Format.rar](https://dl.dropboxusercontent.com/u/15339694/ShareX/2016/09/Impressions.Games.ENG.File.Format.rar)

With HEXEditor is possible see All Text Strings, but a Tool is need for Extract these Text.
## Post #2
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2016-09-26T18:08:05+00:00
- Post Title: [Reqt] Impressions Games .ENG [Caesar/Emperor/Pharaoh/Zeus]

[https://github.com/gaddas/OpenPharaoh](https://github.com/gaddas/OpenPharaoh)

```
//--- 010 Editor v4.0.2 Binary Template
//
// File: Pharaoh_Text.eng
// Author: Danail Dimitrov
// Revision: 1
// Purpose: ENG
//--------------------------------------

LittleEndian();

const ushort MAX_RECORDS = 999;

struct Record
{
    uint32   Offset;
    uint32   Flag;
};

struct Header
{
    char     Type[16];             // The file type
    uint32   RecordsCount;         // Max Records = 999
    uint32   Unknown2;
    uint32   Unknown3;
    uint32   Unknown4;
    uint32   Unknown5;
    Record   Records[MAX_RECORDS];
};

Header header;

```
