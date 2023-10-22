## Post #1
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2015-06-14T08:30:42+00:00
- Post Title: Ori and the blind forest font

Is there a tool for generate this kind of font file? If there a no tools for it then can someone make 010 template for it?
samples [https://www.sendspace.com/file/xjprye](https://www.sendspace.com/file/xjprye)

Original vertical flip tex image
font tex file;sharedassets1~msPGothic_0 distance map.tex
font index file(UTF-16LE);sharedassets1~sharedassets1_4113.-3

Add dds header
resoulution 2048x2048
## Post #2
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2015-06-15T17:25:38+00:00
- Post Title: Ori and the blind forest font

Chinese font[x, width, y, height, (x/yoffset and x/yadvance & chnl&page..?)]
I don't know how to calculate values. No one can make it as 010 template or font generator tool?

samples [https://www.sendspace.com/file/qnn63m](https://www.sendspace.com/file/qnn63m)

```
00 00 10 3D   00 00 8D 3D   00 60 77 3F   00 00 80 3F   C8 65 C5 BC   6C 0F 39 3F   BC D1 54 3F   BC D1 54 3F   F6 90 4B 3F   00 00 00 00   00 00 00 00 
效
00 00 D3 3D   00 00 0B 3E   00 60 77 3F   00 00 80 3F   C8 65 45 BC   6C 0F 39 3F   8D A6 4E 3F   BC D1 54 3F   F6 90 4B 3F   00 00 00 00   00 00 00 00 

下
00 00 00 00   00 00 F8 3C   00 00 50 3D   00 00 A5 3D   C8 65 C5 3C   4A 78 23 3F   9A 3A 3F 3F   03 25 3C 3F   F6 90 4B 3F   00 00 00 00   00 00 00 00 
了
00 00 FC 3C   00 00 74 3D   00 00 50 3D   00 00 A5 3D   C8 65 45 3D   4A 78 23 3F   D4 F9 35 3F   03 25 3C 3F   F6 90 4B 3F   00 00 00 00   00 00 00 00 
已
00 00 76 3D   00 00 B5 3D   00 00 50 3D   00 00 A5 3D   3A BF 76 3D   0F B9 2C 3F   3D E4 32 3F   03 25 3C 3F   F6 90 4B 3F   00 00 00 00   00 00 00 00 
匠
00 00 B6 3D   00 00 F0 3D   00 00 50 3D   00 00 A5 3D   C8 65 45 3D   E1 8D 26 3F   3D E4 32 3F   03 25 3C 3F   F6 90 4B 3F   00 00 00 00   00 00 00 00 

```
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-06-15T21:34:00+00:00
- Post Title: Ori and the blind forest font

this is a unity font.

a tool to calculate distance markers is here - [http://catlikecoding.com/unity/products ... generator/](http://catlikecoding.com/unity/products/distance-map-generator/)

*edit* uh, it doesn't pack the font though. not sure if that is a standard unity thing ?

see post below for new script
## Post #4
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2015-06-15T23:44:58+00:00
- Post Title: Ori and the blind forest font

> Reply from WRS
>
> this is a unity font.

a tool to calculate distance markers is here - http://catlikecoding.com/unity/products ... generator/

*edit* uh, it doesn't pack the font though. not sure if that is a standard unity thing ?

here is a very rough parser

Thanks a lot. However, there are some problems.
Chinese glyph starts at 11D0h. 85 03 00 00 = The number of Chinese glyph.

11D4h, Size 30h ; A1 25 00 00 = □
1204h, Size 30h ; 01 30 00 00 =、
1234h, Size 30h ; 02 30 00 00 = 。
1264h, Size 30h ; 00 4E 00 00 = 一
1294h, Size 30h ; 07 4E 00 00 = 万
12C4h, Size 30h ; 09 4E 00 00 = 三
12F4h, Size 30h ; 0A 4E 00 00 = 上
...
and so on.

[Summary]
I think that '0  ~ 18h' is dummy.
18h ; 0E 00 00 00 ; length of the font name.
1Ch ; adobeHeitiStdR ; name of the font.

The start offset of 1byte glyph is depended on length of the font name.

Chinese font ; adobeHeitiStdR. The number of 1byte glyph offset is 2Ch.


Japanese font ; msPGothic. The number of 1byte glyph offset is 28h.


The number of 1byte glyph is 5E 00 00 00 = 5Eh. (offset 2Ch)
The size of 1byte glyph is 5Eh * 30h = 11A0h.
So, the range of it is 30h~11D0h.

2byte glyph starts at the end of the 1byte glyph.


The number of Chinese glphy is 85 03 00 00 = 385h. (offset 11D0h)
The size of Chinese glphy is 385h * 30h = A8F0h.
So, the range of it is 11D4h ~ BAC4h.



So, I think that template should be edited a little more.
And what 'pack the font' means?
## Post #5
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-06-16T19:44:38+00:00
- Post Title: Ori and the blind forest font

Sorry to hijack the topic for a bit, but how did you manage to unpack the files (I assume you can also repack them as well)?

Please share your info in this topic, it would be appreciated -> [viewtopic.php?f=35&t=12699](http://forum.xentax.com/viewtopic.php?f=35&t=12699)
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-06-16T21:28:36+00:00
- Post Title: Ori and the blind forest font

thanks for your info. the script was written very quickly but i'll update it again with your suggestions: here you go

```
//--- 010 Editor v5.0 Binary Template
//--------------------------------------
// Unity binary font atlas format
// Documented by WRS
//--------------------------------------

struct UnityFontAtlas
{
  uint unknown_0[2];
  uint unknown_1[2];
  uint version; // ?
  uint unknown_02;
  uint len <bgcolor=0x00ff80>;
  char name[len] <bgcolor=0x80ff00>;
  if(len&3)ubyte name_pad[4-(len&3)]; // Aligned to 4 bytes
};

struct UnityGlyph
{
  wchar_t character[2] <bgcolor=0x8080ff>;
  float x,w,y,h; // mult by image dim (512,2048)
  float pool[7]; // other glyph info (kerning, etc)
};

//--------------------------------------

UnityFontAtlas hdr <bgcolor=0xc0c0c0>;

if(hdr.version>1728) { Printf("Warning: May fail to parse\n"); }

uint ascii_count <bgcolor=0xffff00>;
UnityGlyph ascii_glyphs[ascii_count];

uint unicode_count <bgcolor=0xffff00>;
UnityGlyph unicode_glyphs[unicode_count];

local uint rem_count = (FileSize()-FTell()) / sizeof(float);
float tail[rem_count];

//--------------------------------------

Printf("------ Info -------\n");
Printf("Font:    %s\n", hdr.name);
Printf("Ascii:   %d\n", ascii_count);
Printf("Unicode: %d\n", unicode_count);
Printf("Tail:    %d\n", rem_count);

//--------------------------------------
local int used_space = 0;

void Process(UnityGlyph& g, uint d)
{
  local uint x1 = g.x*d;
  local uint x2 = g.w*d;
  local uint y1 = g.y*d;
  local uint y2 = g.h*d;

  local uint space = (y2-y1)*(x2-x1);
  used_space += space;
}

local uint dim = 2048;
local uint i;

i=0;while(i<ascii_count)
{
  Process(ascii_glyphs[i],dim);
  ++i;
}

i=0;while(i<unicode_count)
{
  Process(unicode_glyphs[i],dim);
  ++i;
}

Printf("------ Metrics -------\n");
Printf("Pixels:  %d\n", (dim*dim));
Printf("In-use:  %d\n", used_space);

local float p=(float)used_space/(float)(dim*dim);
Printf("Used:    %.03f%%\n", p);

//--------------------------------------

```


hope this helps
## Post #7
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2015-06-16T23:34:16+00:00
- Post Title: Ori and the blind forest font

> Reply from TheReaperCooL
>
> Sorry to hijack the topic for a bit, but how did you manage to unpack the files (I assume you can also repack them as well)?

Please share your info in this topic, it would be appreciated -> viewtopic.php?f=35&t=12699

Latest unity quickbms script supports unity 5.x [http://aluigi.altervista.org/papers/bms/unity.bms](http://aluigi.altervista.org/papers/bms/unity.bms)
## Post #8
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2015-06-16T23:36:01+00:00
- Post Title: Ori and the blind forest font

> Reply from WRS
>
> thanks for your info. the script was written very quickly but i'll update it again with your suggestions: here you go

hope this helps

Thanks a lot!!
## Post #9
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-06-17T18:42:09+00:00
- Post Title: Ori and the blind forest font

> Reply from adol365
>
> TheReaperCooL wrote:Sorry to hijack the topic for a bit, but how did you manage to unpack the files (I assume you can also repack them as well)?

Please share your info in this topic, it would be appreciated -> viewtopic.php?f=35&t=12699

Latest unity quickbms script supports unity 5.x http://aluigi.altervista.org/papers/bms/unity.bms

Thanks! Although I think it doesn't work, as it extracts lots of the same files, and it overwrites them, plus I can't find some of it. Please pm me with more info if you can! Thanks in advance!
## Post #10
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2015-06-18T02:17:42+00:00
- Post Title: Ori and the blind forest font

> Reply from TheReaperCooL
>
> adol365 wrote:TheReaperCooL wrote:Sorry to hijack the topic for a bit, but how did you manage to unpack the files (I assume you can also repack them as well)?

Please share your info in this topic, it would be appreciated -> viewtopic.php?f=35&t=12699

Latest unity quickbms script supports unity 5.x http://aluigi.altervista.org/papers/bms/unity.bms

Thanks! Although I think it doesn't work, as it extracts lots of the same files, and it overwrites them, plus I can't find some of it. Please pm me with more info if you can! Thanks in advance!

Duplicated files are needless things for making translation patch. Just use a option to overwrite it.
## Post #11
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-06-18T09:14:43+00:00
- Post Title: Ori and the blind forest font

> Reply from adol365
>
> Duplicated files are needless things for making translation patch. Just use a option to overwrite it.

Okay, but I can't seem to find the string files, as most Unity games use .bcg files, and this one doesn't have, yet when I open up the files in a HEX Editor I can find in-game text lying around here and there. And I still can't import them back in
## Post #12
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2015-07-07T09:17:40+00:00
- Post Title: Ori and the blind forest font

[Subject: Ori and the blind forest font](http://forum.xentax.com/viewtopic.php?p=106851#p106851)

> Reply from adol365
>
> Is there a tool for generate this kind of font file? If there a no tools for it then can someone make 010 template for it?
samples https://www.sendspace.com/file/xjprye

Original vertical flip tex image
font tex file;sharedassets1~msPGothic_0 distance map.tex
font index file(UTF-16LE);sharedassets1~sharedassets1_4113.-3

Add dds header
resoulution 2048x2048

Hi! Could you help me repack .assets file? Thanks!
## Post #13
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2015-07-07T09:33:31+00:00
- Post Title: Ori and the blind forest font

You can use bms script. [http://aluigi.altervista.org/papers/bms/unity.bms](http://aluigi.altervista.org/papers/bms/unity.bms)
## Post #14
- Username: akala
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Nov 14, 2015 7:39 pm
- Post datetime: 2015-12-15T13:05:42+00:00
- Post Title: Ori and the blind forest font

Hi! I want to add new character to this English font in game. (F.E. "ğ" "ı")

sharedassets1_00002.-3
candara_0 distance map.tex

How I can do that?

I read the all topic but I don't understand much. How I get font pic? and edit distance? and import?

I can't open tex files.

Edit:

Never mind, I used to other game fonts, looks fine.
