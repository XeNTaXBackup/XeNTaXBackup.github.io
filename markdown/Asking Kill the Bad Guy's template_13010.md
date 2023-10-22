## Post #1
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2015-07-01T17:16:56+00:00
- Post Title: Asking Kill the Bad Guy's template

Hi, I need some help. samples [https://www.sendspace.com/file/yx5kik](https://www.sendspace.com/file/yx5kik)
-1 is font mapping file.
And the resoultion of ArialBig_0 is 4098x2048 and ArialMedium_0 is 2048x2048.

For example, ArialMedium_0...
The number of glyph starts at 20h.
After that 'wchar_t character[2]' starts.


0x24 + 156C(=0x55B * 0x4) = 0x1590

At the end of it, there is the number of glyph value again. 0x1590
After that 'struct  uCharData' starts. 40h. Maybe Xposition ,.etc.


However, I don't know how to write 010 template when glyph and uCharData is splitted.
## Post #2
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2015-07-01T20:15:20+00:00
- Post Title: Asking Kill the Bad Guy's template

Try this: [https://yadi.sk/d/tS3m2yhjhcGEJ](https://yadi.sk/d/tS3m2yhjhcGEJ) (bin fnt + textures)
## Post #3
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2015-07-01T21:19:31+00:00
- Post Title: Asking Kill the Bad Guy's template

> Reply from makcar
>
> Try this: https://yadi.sk/d/tS3m2yhjhcGEJ (bin fnt + textures)
What do you mean 'try this'? My question is how to write template for it when character and uChardata was splitted. Not a file.
This is not that I expected and there are no fonts for my own language.
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-07-03T22:29:33+00:00
- Post Title: Asking Kill the Bad Guy's template

not a lot of time again   

here you go:

```
//--- 010 Editor v5.0 Binary Template
//--------------------------------------

// Go to offset 20h
FSeek(0x20);

// Read 32-bits as an unsigned integer
// This is the number of UnityCharacter structs
uint GlyphCount <bgcolor=0x00ff00>;

// Read 2 wide characters as an array of GlyphCount
struct Character {
  wchar_t character[2];
} Glyphs[GlyphCount] <bgcolor=0xffff00>;

// Read 32-bits as an unsigned integer
// This *should* match GlyphCount
uint InfoCount <bgcolor=0x00ff00>;

// Check these are the same
Assert(GlyphCount == InfoCount, "Does not match!");

// The 64-byte info structure (floats?)
struct Info {
  float un1;
  float un2;
  float un3;  // 0?
  float un4;
  float un5;
  float un6;  // 0?
  float x1;
  float y1;
  float un9;  // 0?
  float x2;
  float y2;
  float un12;
  float un13;
  float un14;
  float un15;
  float un16;
} GlyphInfo[InfoCount] <bgcolor=0x8080ff>;


```
## Post #5
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2015-07-05T05:39:18+00:00
- Post Title: Asking Kill the Bad Guy's template

> Reply from WRS
>
> not a lot of time again   

here you go:
Code: Select all//--------------------------------------
//--- 010 Editor v5.0 Binary Template
//--------------------------------------

// Go to offset 20h
FSeek(0x20);

// Read 32-bits as an unsigned integer
// This is the number of UnityCharacter structs
uint GlyphCount <bgcolor=0x00ff00>;

// Read 2 wide characters as an array of GlyphCount
struct Character {
  wchar_t character[2];
} Glyphs[GlyphCount] <bgcolor=0xffff00>;

// Read 32-bits as an unsigned integer
// This *should* match GlyphCount
uint InfoCount <bgcolor=0x00ff00>;

// Check these are the same
Assert(GlyphCount == InfoCount, "Does not match!");

// The 64-byte info structure (floats?)
struct Info {
  float un1;
  float un2;
  float un3;  // 0?
  float un4;
  float un5;
  float un6;  // 0?
  float x1;
  float y1;
  float un9;  // 0?
  float x2;
  float y2;
  float un12;
  float un13;
  float un14;
  float un15;
  float un16;
} GlyphInfo[InfoCount] <bgcolor=0x8080ff>;

Thank you!
