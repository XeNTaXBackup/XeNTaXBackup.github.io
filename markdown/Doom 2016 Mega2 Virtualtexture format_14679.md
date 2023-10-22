## Post #1
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-07-24T19:23:11+00:00
- Post Title: Doom 2016 Mega2 Virtualtexture format

Because DOOM uses Id's Tech6 engine, the format is completely different than Id's Tech5 engine. but there are a lot of similarities.

Here's what I have so far:

```
//--- 010 Editor v5.0 Binary Template
//
// File: Doom mega2 virtualtexture
// Author: Volfin
// Revision: 1.0
// Purpose:
//--------------------------------------
LittleEndian();

typedef struct QuadTreeLevelRecord1
{
    ulong unknown1;
    ulong unknown2;
    ulong block_width;
    ulong block_height;
    ulong QuadPointer_start;
    ulong QuadPointer_length;
};

typedef struct dataPointers1
{
    uint64 Compressed_Offset;
    uint64 Compressed_Length;
};

 struct Pages_File { 
    char Signature[4]; // Signatuer ID 0xA63FBB21
    ulong texture_count_maybe;
    ulong unknown2; 
    ulong level_count;
    ulong x_resolution;
    ulong y_resolution;
    ulong block_width;
    ulong block_height;
    ulong x_resolution;
    ulong y_resolution;
    ulong block_width;
    ulong block_height;
    ulong unknown7;
    ulong QuadTreeLevelCount;
    uint64 Pointer_offsets_table; // at bottom, large offsets
    uint64 Quadtree_offset_table;
    ulong Pointer_offsets_count;
    ulong Quadtree_offset_count;

local int j;
local int i=0;

    for (j=0;j<MegaTexture.QuadTreeLevelCount;j++)
    {
        // Lists start and length of each section (or leaf) of the quadtree. usually 12 levels.
        QuadTreeLevelRecord1 record1;
    }

// jump to middle to read that table
FSeek(MegaTexture.Quadtree_offset_table);

typedef struct
{
    for (j=0;j<MegaTexture.Quadtree_offset_count;j++)
    {
        ulong QuadPointer_into_DataPointers;
    }
}QP1;

// Quadtree data of leaf contents, points to entries in DataPointers.
QP1 QuadPointers;

// jump to bottom to read that table
FSeek(MegaTexture.Pointer_offsets_table);

typedef struct
{
    for (j=0;j<MegaTexture.Pointer_offsets_count;j++)
    {
        dataPointers1 DataPointer;
    }
}DP1;

//list of pointers to compressed data blocks (offset + length)
DP1 DataPointers;

// jump to a sample compressed block
FSeek(DataPointers.DataPointer[4].Compressed_Offset);

// example compressed image block (120x120 pixels effective, 128x128 pixels actual)
// Note, Compressed blocks always seem to start with 0x0C1E1E1E, a sub-record header maybe?
char comppressedData4[DataPointers.DataPointer[4].Compressed_Length];


} MegaTexture;

```


As before it's arranged in a quad tree. However, they structured the data differently. There are 5 major sections:

1) the Data header. this contains general information, pointer to the PointerOffsets Table and pointer to the QuadPointers table.
2) the QuadtreeLevel Records. These follow directly after the Data header, and there is a count of how many records there are in the Data header. These provide offset/length data defining which blocks in the QuadPointers table belong to this particular level.
3) the QuadPointers Table. This is a simple list of pointers, defining which entries in the DataPointers Table correspond to entries in the QuadtreeLevel Records.
4) the DataPointers Table. This is a list of Offset/Length pairs that defines blocks of compressed image data.  From investigation it's assumed each block represents 120x120 pixels effective, 128x128 pixels actual.  It's also noted that each compressed block always seems to start with 0x0C1E1E1E, a sub-record header may exist.
5) the compressed data itself.  this resides between the end of the QuadtreeLevel Records and the start of the QuadPointers Table.

At this time there's still a lot of unknown factors.  Is the image codec the same as that used in Tech5, or something new? How are image layers arranged, and how many layers are there?  etc. etc.

If anyone finds any more information, or fills out some of the unknowns in the template, or sees any mistakes, please post here so we can build up more knowledge.
