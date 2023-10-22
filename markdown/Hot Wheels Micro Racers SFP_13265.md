## Post #1
- Username: aaro4130
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Aug 23, 2011 10:01 am
- Post datetime: 2015-08-30T20:39:24+00:00
- Post Title: Hot Wheels Micro Racers SFP

Hey! I'm trying to look into this format but it's out of my level. Currently all I know is this about it :

header:

```
long marker1; //always 1
long unknown; //never the same
long marker2; //always 2
long unknown2; //always the same
long marker3; //always 3

```


I've seen filenames throughout the files, but can't find a file table, offset to one, etc. Looks like some files are .TGA and some are compressed with WTGA. The only information I can find on wtga is this : [http://www.verycomputer.com/155_b0804d5 ... 4_1.htm#p1](http://www.verycomputer.com/155_b0804d556e2ab5a4_1.htm#p1)

I have sample SFP's at [http://mmarchive.com/aaro4130/SFP](http://mmarchive.com/aaro4130/SFP) if anyone can take a look for me. They're all <2MB each.
## Post #2
- Username: Allen
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Feb 17, 2012 4:49 pm
- Post datetime: 2015-08-31T09:07:19+00:00
- Post Title: Hot Wheels Micro Racers SFP

SFP is a chunk-based format.
You can export the resource according to ID.

```
//--- 010 Editor v6.0.1 Binary Template
//
// File:2015-8-31 Hot Wheels Micro Racers SFP
// Author:Allen
// Revision:
// Purpose:
//--------------------------------------


//chunk id 1 is file

//chunk id 2 is 1's sub chunk
//chunk id 3 is 2's sub chunk, is a image data chunk.256 color Palette format.
//chunk id 0xE is 2's sub chunk, is a string table. CString(null-terminator).
//chunk id 0xF is 2's sub chunk, is a string's offset table(offset to 0xE chunk).

//chunk id 4 is 1's sub chunk
//chunk id 5 is 4's sub chunk
//chunk id 6 is 4's sub chunk
//chunk id 7 is 4's sub chunk,  a string table.4 bytes alignment, zero fill not enough.
//chunk id 0xB is 4's sub chunk

//Basic Struct:
typedef struct {
DWORD   chunkSize;
DWORD   chunkID;
byte    chunkData[chunkSize-8];
}chunk;


typedef struct {
DWORD   chunkSize;
DWORD   chunkID;
}chunkIndex;

chunkIndex File;
local DWORD chunkEndOfs = FTell()+File.chunkSize-8;
while(FTell()<chunkEndOfs)
{
    chunkIndex Index;
    if (Index.chunkID==2)
    {
        local DWORD chunk2EndOfs = FTell()+Index.chunkSize-8;
        while(FTell()<chunk2EndOfs)
        {
            chunk ID2SubChunk;
        }
    }
    if (Index.chunkID==4)
    {
        local DWORD chunk4EndOfs = FTell()+Index.chunkSize-8;
        while(FTell()<chunk4EndOfs)
        {
            chunk ID4SubChunk;
        }
    }
}
```
## Post #3
- Username: aaro4130
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Aug 23, 2011 10:01 am
- Post datetime: 2015-08-31T16:40:52+00:00
- Post Title: Hot Wheels Micro Racers SFP

Wow man! Thanks so much . Gonna see if I can find out what any of the sub chunks are, on top of the ones you already found.
