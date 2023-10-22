## Post #1
- Username: strikestar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 07, 2016 5:55 pm
- Post datetime: 2016-01-07T10:03:28+00:00
- Post Title: Extract resourses from .SAR files

Hello! How to extract resourses from files ZELRES1.SAR, ZELRES2.SAR, ZELRES3.SAR from game Zeliard? I need image sprites and other game resousres, please help me!


 ZELRES1.zip
(135.08 KiB) Downloaded 18 times
## Post #2
- Username: heksesang
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 17, 2014 10:12 pm
- Post datetime: 2016-01-27T01:46:57+00:00
- Post Title: Extract resourses from .SAR files

```
{
    local uint32 offset = 0;
    local uint32 count = 0;
    
    do
    {
        uint32 Entry;
    } while ((offset = ReadUInt()) > Entry[count++]);
} SARChunkTable;

typedef struct
{
    uint32 size;
    byte data[size] <optimize=false>;
} SARChunk;

uint32 GetTableSize(SARChunkTable &table)
{
    return sizeof(table) / sizeof(table.Entry);
};

typedef struct
{
    SARChunkTable table;
    SARChunk chunk[GetTableSize(table)] <optimize=false>;
} SARFile;

```


That's as much as I have figured out. First chunk seems to contain strings and some filename list.
