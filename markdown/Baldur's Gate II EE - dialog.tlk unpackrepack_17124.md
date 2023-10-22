## Post #1
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2017-10-11T18:38:56+00:00
- Post Title: Baldur's Gate II EE - dialog.tlk unpack/repack

Hi,

I want to translated this game, but I can't open this file. 

I search form and find nothing 

Sample: [http://www.mediafire.com/file/p4y9bouji ... dialog.tlk](http://www.mediafire.com/file/p4y9bouji1ld3c3/dialog.tlk)

Please help.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-10-13T23:45:55+00:00
- Post Title: Baldur's Gate II EE - dialog.tlk unpack/repack

dead simple format

```
//--- 010 Editor v5.0 Binary Template
//
// File: dialog.tlk
// Author: wrs
// Revision: 1
// Purpose: parse dialog.tlk
//--------------------------------------

byte fluff[10]; // magic "TLK V1  \0\0"
uint num;
uint offset; // absolute

struct info
{
  short rev;
  char ref[8];
  int zero1, zero2; Assert(zero1==0); Assert(zero2==0);
  int offset; // absolute
  int length;
} a[num] <optimize=false>;

byte data[FileSize()-offset];
Assert(FEof());

```
## Post #3
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2017-10-14T19:12:30+00:00
- Post Title: Baldur's Gate II EE - dialog.tlk unpack/repack

> Reply from WRS
>
> dead simple format
Code: Select all//--------------------------------------
//--- 010 Editor v5.0 Binary Template
//
// File: dialog.tlk
// Author: wrs
// Revision: 1
// Purpose: parse dialog.tlk
//--------------------------------------

byte fluff[10]; // magic "TLK V1  \0\0"
uint num;
uint offset; // absolute

struct info
{
  short rev;
  char ref[8];
  int zero1, zero2; Assert(zero1==0); Assert(zero2==0);
  int offset; // absolute
  int length;
} a[num] <optimize=false>;

byte data[FileSize()-offset];
Assert(FEof());

Thx a lot. But how do I use 010 Editor?
Can you share extract.cmd for this?
