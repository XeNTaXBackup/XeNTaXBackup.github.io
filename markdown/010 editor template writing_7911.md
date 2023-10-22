## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-21T22:16:36+00:00
- Post Title: 010 editor template writing

So on my journey towards finding an outline writing standard that I liked, I thought of writing templates for 010 editor since that would allow me to (1) write an outline in a standard format, and (2) compare it against other files quickly

So I looked at the syntax in the help file and quickly wrote something together, but the output didn't look very nice.

Here's a model format:

```
//--- 010 Editor v3.1.3 Binary Template
//
// File: Gates of Anderon TMH
// Author: Tsukihime
// Revision: 1.0
// Purpose: Outline
//--------------------------------------
struct File {
    
    SetForeColor( cRed );
    struct Header {
        int unk1;
        int count;
        int unk2;
        byte unk3;
        float unk[4];
    } header;

    SetForeColor( cBlue );
    struct Mesh {
        int numVerts;
        struct Vertex {
            float coords[3];
            float unk[7];
        } vertex[numVerts];
        int unk;
        int numIndex;
        short unk;
        short index[numIndex];
    } mesh;
} file;

```


Here, there are structs defined within structs, all defined within the File struct which seems kind of silly. I've tried to apply color to it to make it easier to pick out which part is what, but adding one color for an entire struct does not seem too useful in the long-run.

It'd probably be better if each struct were defined separately and then I could just refer to them in a "main" struct.

Anyone have ideas on how to make a wall of hex look pretty (and useful)?
## Post #2
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-23T00:39:34+00:00
- Post Title: 010 editor template writing

Here's a section from My 010 Template for GR2 files.

typedef struct {    // GR2ih
    UINT  File_format_revision <format=decimal>;
    UINT  File_Size_in_bytes;
    UINT  CRC <format=hex,comment="CRC of file (from begin of section array up to EoF). Algoritm CRC-32">;
    UINT  SectionArrayOffset <bgcolor=0xffffb0,fgcolor=cRed,comment="Offset to section array">;   --------------------------- Note the color references
    UINT  SectionArrayCount <comment="Total number of sections">;
    UINT  Unknowns[4]<hidden=true,format=hex>;
    UINT  Tag<format=hex>;
    UINT  Unknown[8]<hidden=true,format=hex>;
} GR2INFOHEADER;
