## Post #1
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2015-01-28T16:53:18+00:00
- Post Title: [REQ][PC] Zanzarah - help with fbs file format

Hello. I'm trying to guess specification of text file format from Zanzarah.

I have already something like this:
[http://s5.postimg.org/fmx6228t3/screenshot002711.jpg](http://s5.postimg.org/fmx6228t3/screenshot002711.jpg)

// FILE HEADER
uint32 {4}   - number of text lines (?)

// DATA
  //for each entry
  uint32 {4}   - pointer (?)
  these bytes {12} - 030000000000000000000000  almost always the same (?)
  uint32 {4}   - size of the text with null on the end
  char {X}     - text
  these bytes {8} - 0100000001000000 i think that always the same (?)
  uint32 {4} - 04000000, sometimes 8 bytes (?)
 char {1} - 00, 0A or 07 (?)
these bytes - 00000000000000020000000100000000 (?)

This is my first guessing with text files, so i can be wrong :p Can you tell me what are the values marked with question mark?

Here are the file and the color map for Hex workshop: [http://ikskoks.playloc.pl/XENTAX/Zanzarah_Xentax.rar](http://ikskoks.playloc.pl/XENTAX/Zanzarah_Xentax.rar)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2015-01-30T00:25:17+00:00
- Post Title: [REQ][PC] Zanzarah - help with fbs file format

Nevermind. I solved my problem. 

And the file format goes like this:

// FILE HEADER
uint32 {4} - number of text lines
uint32 {4} - unknown
uint32 {4} - unknown
uint32 {4} - unknown
uint32 {4} - unknown

// DATA
//for each entry
uint32 {4} - size of the text with null
char {X} - text
uint32 {4} - unknown
uint32 {4} - unknown
uint32 {4} - unknown
uint32 {4} - unknown
uint32 {4} - unknown
uint32 {4} - unknown
uint32 {4} - value, if equal or greater than 3, exception (different size) should occur 
??? - unknown, different sizes, depend on the value above
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-30T21:12:18+00:00
- Post Title: [REQ][PC] Zanzarah - help with fbs file format

your header is wrong.

a parser for your format:

```
//--- 010 Editor v6.0 Binary Template
//--------------------------------------

#include "prelen.bt"

uint LineCount;

struct LineInfo
{
    uint un1_1, un1_2, un1_3, un1_4;
    str text1(plen32);
    uint un2_1, un2_2, un2_3, un2_4, un2_5, un2_6;
    str text2(plen32);
}
Lines[LineCount] <optimize=false>;

```
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2015-01-30T21:38:15+00:00
- Post Title: [REQ][PC] Zanzarah - help with fbs file format

Thank you 

In my last post was information "Nevermind. I solved my problem". I wrote my own tools and they are working fine [http://s5.postimg.org/9094mrcbb/zanthp_ ... _15_67.jpg](http://s5.postimg.org/9094mrcbb/zanthp_2015_01_30_16_20_15_67.jpg)

But still thanks
## Post #5
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2015-02-01T15:35:05+00:00
- Post Title: [REQ][PC] Zanzarah - help with fbs file format

> Reply from ikskoks
>
> Thank you 

In my last post was information "Nevermind. I solved my problem". I wrote my own tools and they are working fine http://s5.postimg.org/9094mrcbb/zanthp_ ... _15_67.jpg

But still thanks

Welcome to the CHUJ. xD 
I see what you did there.
