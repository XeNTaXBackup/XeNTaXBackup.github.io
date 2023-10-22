## Post #1
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2016-04-12T14:53:52+00:00
- Post Title: Radiation Island .str file

Anyone can help me, please ? Thanks
[strings_EN.zip](https://xentaxbackup.github.io/file/10758_strings_EN.zip)
## Post #2
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2016-04-14T04:59:14+00:00
- Post Title: Radiation Island .str file

anyone can help me ? Thanks
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-04-14T22:35:40+00:00
- Post Title: Radiation Island .str file

```
//--- 010 Editor v5.0 Binary Template
//
// File:     strings_EN.str
// Author:   wrs
// Revision: 1
// Purpose:  read entire file
//--------------------------------------
uchar hdr[6];
ushort num;

uint vals[num +1];

struct str(int len)
{
  wchar_t xor_str[len];
  // xored by 0x63?
};

local int i=0;

while(i<num)
{
  str String(vals[i+1]-vals[i]);
 ++i;
}

Assert(FTell() == FileSize());


```


resulting strings do not look english!
## Post #4
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2016-04-15T03:29:39+00:00
- Post Title: Radiation Island .str file

> Reply from WRS
>
> Code: Select all//--------------------------------------
//--- 010 Editor v5.0 Binary Template
//
// File:     strings_EN.str
// Author:   wrs
// Revision: 1
// Purpose:  read entire file
//--------------------------------------
uchar hdr[6];
ushort num;

uint vals[num +1];

struct str(int len)
{
  wchar_t xor_str[len];
  // xored by 0x63?
};

local int i=0;

while(i<num)
{
  str String(vals[i+1]-vals[i]);
 ++i;
}

Assert(FTell() == FileSize());



resulting strings do not look english!

Thanks so much. But do you think this file is encrypted ???
## Post #5
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2016-04-21T05:04:12+00:00
- Post Title: Radiation Island .str file

anyone can help ? Thanks
## Post #6
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2016-04-30T08:57:13+00:00
- Post Title: Radiation Island .str file

please give me a help
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-05-03T21:16:04+00:00
- Post Title: Radiation Island .str file

sorry no idea how to decode those strings

```
//--- 010 Editor v5.0 Binary Template
//
// File:     strings_EN.str
// Author:   wrs
// Revision: 1
// Purpose:  read entire file
//--------------------------------------
uchar hdr[6];
ushort num;

uint vals[num +1];


struct xorstr(int len)
{
  wchar_t xor_str[len];
  local int str_len = len;
};

typedef xorstr xstr <read=GetXorString>;

string GetXorString(xstr &t)
{
  wstring res = L"";

  local int l=0;
  while(l < t.str_len) {
    res += (wchar_t)(((uint)t.xor_str[l]) ^ 0x6363); ++l;
  }
  
  return WStringToString(res, CHARSET_ANSI );
}

local int i=0;

while(i<num)
{
  xstr String(vals[i+1]-vals[i]);
++i;
}

Assert(FTell() == FileSize());


```
