## Post #1
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2015-01-03T00:09:01+00:00
- Post Title: Middle-earth Shadow of Mordor font

Hi guys!
Can anyone help me with this font file?

Download

```
https://mega.co.nz/#!f04WXTSR!iJ_MfTWUZX5kqwsyROGvZGkAIyRnZDYNgNF4PtWUMk8
```


and... this is what i think thing.

```
//--- 010 Editor v6.0 Binary Template
//
// File: font_latin.gfx
// Author: MiRiKan
// Revision: 0.1
// Purpose: Middle-earth Shadow of Mordor Font File
//--------------------------------------
LittleEndian();

local uint pos, x;
local uint realheader;
local uint count = 0;

char identity[3] <open=suppress>;
ubyte unk;
uint sizeOfgfx;

struct dummy1{
    uint64 dummy;
    uint64 dummy;
    uint64 dummy;
}unk <hidden=true>; //they are dummys cause i checked with japanese font

byte sizeOf_fontType;
char fontType[sizeOf_fontType] <open=suppress>;
uint16 dummy <hidden=true>;

struct dummy2{
    uint64 nuknow;
    uint unknow;
}unk <hidden=true>; //they are dummys cause i checked with japanese font

byte unk;

uint secondstart;
uint unknow <hidden=true>;

//start first font
byte sizeOf_fontName;
char fontName[sizeOf_fontName] <open=suppress>;
uint16 totalOfchar;

realheader = FTell();
struct charData{ //might be images?
    for(x = 0; x < totalOfchar; x++){
        struct Char{
            uint PointerOrSomething;
            pos = FTell();
            FSeek(PointerOrSomething + realheader);
            uint16 POS_;
            FSeek(pos);
            count++;
        }data;
    }
}DATA;
uint startchars;
uint dontneedchange;

pos = startchars + realheader;
FSeek(pos);

struct chars{ //list of chars
    for(x = 0; x < totalOfchar; x++){
        wchar_t getchat();
    }
}CHARS;
uint16 donotchange;
uint temp;

//maybe end of first font?
//second font will start at secondstart + realheader.
```
## Post #2
- Username: MiRiKan
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-01-03T10:16:58+00:00
- Post Title: Middle-earth Shadow of Mordor font

Wrong mate  Fonts are Autodesk GFX V2 format. Not that hard to edit. PM me
## Post #3
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2015-01-04T03:38:02+00:00
- Post Title: Middle-earth Shadow of Mordor font

> Reply from michalss
>
> Wrong mate  Fonts are Autodesk GFX V2 format. Not that hard to edit. PM me

wow! thanks!
i sent you PM
