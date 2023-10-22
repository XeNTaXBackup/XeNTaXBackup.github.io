## Post #1
- Username: MuratG
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Oct 28, 2014 7:56 am
- Post datetime: 2017-05-25T07:40:13+00:00
- Post Title: NieR Automata .mdc files

Menu and shop\.mcd
ui\.mcd



010 editor with How to edit .mcd files? Please help.

```
//--- 010 Editor v5.0 Binary Template
//
// File:
// Author:
// Revision:
// Purpose:
//--------------------------------------
typedef struct
{
  long offset_string_table <format=hex>;
  long count_string_table;
  long offset_symbol_codes <format=hex>;
  long count_symbol_codes;
  long offset_symbol_table <format=hex>;
  long count_symbol_table;
  long offset_fonts_table <format=hex>;
  long count_fonts_table;
  long offset_unk2 <format=hex>;
  long count_unk2;
} Header;
/*
typedef struct
{
  long s_offset <format=hex>;
  long unk2;
  long unk3;
  long s_id;
} string_table;
*/
typedef struct
{
  uint16  ct_fontid;
  wchar_t ct_char;
  long    ct_code;
} code_table;

typedef struct
{
  long texid;
  float i1;
  float i2;
  float i3;
  float i4;
  float w;
  float h;
  long z1;
  long z2;
  long z3;
} symbol_table;

LittleEndian();
RequiresVersion(4,0);

SetBackColor( cLtAqua );
Header hdr;

SetBackColor( cLtYellow );
local int i = 0;
local long pos1, pos2, pos3;

FSeek(hdr.offset_string_table);
struct
{
  SetBackColor( cLtYellow );
  long s_offset <format=hex>;
  long s_entrycount;
  long s_unk3;
  long s_id;

  pos1 = FTell();
  FSeek(s_offset);
  struct 
  {
    SetBackColor( 0xFF934C );
    long se_offset <format=hex>;
    long se_blockcount;
    long se_dummy;  // = 0 dummy?
    long se_totallength;
    long se_fontid;
    pos2 = FTell();
    FSeek(se_offset);
    struct
    {
      SetBackColor( 0xFF00B2);
      long   be_offset <format=hex>;
      long   be_prev_block_len; // prev block length?
      long   be_length;
      long   be_length2; // = vl_length+1
      int64  be_line_height;

      pos3 = FTell();
      FSeek(be_offset);
      struct
      {
        SetBackColor( 0xFF9400);
        struct
        {
          uint16 lo;
          uint16 hi;
        } data[be_length];
        uint16  wend;   
      } value <optimize=false>;  
      
      FSeek(pos3); 
    } block_entry[se_blockcount] <optimize=false>;

    FSeek(pos2);
  } string_entry[s_entrycount] <optimize=false>;

  FSeek(pos1); 

} string_table[hdr.count_string_table] <optimize=false>;

FSeek(hdr.offset_symbol_codes);
SetBackColor( cLtPurple );
code_table codes[hdr.count_symbol_codes];

FSeek(hdr.offset_symbol_table);
SetBackColor( cLtGreen );
symbol_table symbols[hdr.count_symbol_table];

FSeek(hdr.offset_fonts_table);
SetBackColor( cYellow );
struct
{
  long  ft_fontid;
  float ft_glyph_width;
  float ft_glyph_height;
  float ft_kern_y;
  float ft_kern_x;
} fonts_table[hdr.count_fonts_table];

FSeek(hdr.offset_unk2);
SetBackColor( cLtRed );
struct
{
  struct
  {
    long ut2_unk1;
    long ut2_unk2;
    char ut2_name[32];
  } table2_entry[hdr.count_unk2] <optimize=false>;
} unk_table2;
string ReadEntry(long id, byte hip)
{
  local string c, c1;

  local uint16 r;
  local int k, i, d = 0;
  local char b;

  SPrintf(c, "%sID %d:", c, string_table[id].s_id);
  
  local int v = 0;
  while (true)
  {
    SPrintf(c, "%s\n      Entry %3d: ", c, v);
    d = 0;
    k = 0;
    while (true)
    {
      i = 0;
      c1 = "";
      while (i != string_table[id].string_entry[v].block_entry[d].be_length)
      {
        b = 0;
        r = string_table[id].string_entry[v].block_entry[d].value.data[i].lo;
        k = 0;
        while (k != hdr.count_symbol_codes)
        {
          if (r == codes[k].ct_code)
          {
            b = codes[k].ct_char;
            break;
          }
          k++;
        }
        if (r == 0x8001)
        {
          b = ' ';
        }
        if (b != 0)
          if (hip)
            SPrintf(c, "%s %4s",c,b);
          else
            c = c + b;
        else
          SPrintf(c, "%s(%d)", c, r);
        // hi part of struct
        if (hip)
        {
          r = string_table[id].string_entry[v].block_entry[d].value.data[i].hi;  
          //if (r > 0)
          SPrintf(c1, "%s %04x", c1, r);  
        }
        i++;
      }
      d++;
      if (hip)
        c = c+"\n\t"+c1;
      if (d == string_table[id].string_entry[v].se_blockcount)
        break;
      c = c+"\n                 ";
    }
    v++;
    if (v == string_table[id].s_entrycount)
      break;
  }
  return c;
}

local int z = 0;

while (z != 23)
{
  Printf("\n%s", ReadEntry(z, 0));
  z++;
}

/*
local int k;
while (z != hdr.count_symbol_table)
{
  k = 0;
  while (k != hdr.count_symbol_table)
  {
    if (z == (codes[k].ct_code))
      Printf("%d: %c (%d) = %d / %d\n", z, codes[k].ct_char, codes[k].ct_char, codes[k].ct_code, codes[k].ct_unk1);
    k++;
  }
  z++;
}
*/
```

[mcd sample.rar](https://xentaxbackup.github.io/file/12941_mcd sample.rar)
