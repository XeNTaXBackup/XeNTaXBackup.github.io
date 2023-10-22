## Post #1
- Username: flyingturtle
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 29, 2016 1:41 pm
- Post datetime: 2016-10-29T05:44:32+00:00
- Post Title: Forza Horizon 2 Xbox (.Str)

How can i decrypt this file for editing?

Header is LSB2.
[Tracks.rar](https://xentaxbackup.github.io/file/11849_Tracks.rar)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-10-30T01:01:15+00:00
- Post Title: Forza Horizon 2 Xbox (.Str)

reallllllllllllllllllly lazy day - here you go:

```
get DUMMY long # 1
get DUMMY long # 2
endian big
get DUMMY long # 36 (header size)
get DUMMY long # 4
get DUMMY long # 36 (header size)

get OFFSET_EOTEXT long
get DUMMY long # 0
get OFFSET_EODATA long

# --------------- 36

get OFFSET_UN long
get COUNT long
get DUMMY long # 808?
get DUMMY long # 0

# string offsets:
# ushort ?
# offset (x2 to get 'end of wstring' length)

# string offsets * COUNT

# strings:
# array of nul-terminated wide strings * COUNT

# unknown:
get DUMMY long
get DUMMY long
# uint * (COUNT * 2)

# ids:
# array of nul-terminated strings * COUNT

# tail:
get SIZE long
get NUM long # dupe of COUNT
# uint * (NUM * 2)

# eof reached!

```
## Post #3
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2016-10-31T19:10:43+00:00
- Post Title: Forza Horizon 2 Xbox (.Str)

I had trouble with this script and the above file. I've never dealt with localization decoding. Is this to be used with QuickBMS?
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-10-31T22:08:21+00:00
- Post Title: Forza Horizon 2 Xbox (.Str)

> Reply from Teancum
>
> I had trouble with this script and the above file. I've never dealt with localization decoding. Is this to be used with QuickBMS?

correct - it is a bms script for quickbms which describes the entire file format from the sample file.

as a script it doesn't actually do anything though - quickbms isn't really good for unpacking/repacking localisation files so none of the strings are extracted here.

if either of you are actually interested i can write up a tool

edit here is a better script for 010 editor:

```
//--- 010 Editor v5.0 Binary Template
//
// File:     tracks.str
// Author:   wrs
// Revision: 1
// Purpose:  str files from forza horizon 2
// Link:     http://forum.xentax.com/viewtopic.php?f=35&t=15422
//--------------------------------------

// ------------
// xbox style:
BigEndian();

// ------------
// string helpers:
struct wstr{ wstring val; };
struct cstr{ string val; };

// ------------

struct
{
  char Magic[4]; // LSB2
  uint one; // 1 little endian
  uint two; // 2 little endian
  uint un_36; // block_head size?
  uint un_4;

// these offsets are absolute:
  uint offset_blockStrings;
  uint offset_blockIds;
  uint unknown_0; // ?? zero
  uint offset_blockTail;

} BLOCK_HEAD;

// ------------

struct
{
  uint block_size;
  uint num;

  struct
  {
    ushort Id;
    uint OffsetHalf; // halved
  } x[num +1];

  struct
  {
    wstr x[num +1] <optimize=false>;
  } STRS;

} BLOCK_STRING;

// ------------



struct id_info
{
  ushort a, b, c, d;
};

// ------------

struct
{
  uint blocksize;
  uint num;

  id_info unknown_info [num];

  struct
  {
    cstr x[num] <optimize=false>;
  } str_ids;

} BLOCK_IDS;

// ------------

struct
{
  uint blocksize; // (num*ushort) +8
  uint num;
  ushort tail[num];
} BLOCK_TAIL;

// sanity:
Assert(FEof());


```


edit 2

removed string.bt - it isn't required!
