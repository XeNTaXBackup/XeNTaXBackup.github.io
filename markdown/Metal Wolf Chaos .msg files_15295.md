## Post #1
- Username: SonofUgly
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Feb 25, 2012 9:43 pm
- Post datetime: 2016-09-29T04:31:14+00:00
- Post Title: Metal Wolf Chaos *.msg files

Wondering if anyone could make a tool for these, convert them to and from a basic text form like:

```
000013F1 - Clear Time
...
```

They seem pretty simple, and a lot like Rockstar's gxt/gxt2 language files.
A couple of sample files: [http://www.mediafire.com/file/2r6h9s1b3 ... amples.rar](http://www.mediafire.com/file/2r6h9s1b3d2hfr6/MWC_msg_samples.rar)

Here's the basic idea, from what I can tell: [http://i.imgur.com/3n8YkoA.png](http://i.imgur.com/3n8YkoA.png)
The part there that I'm not sure about I think might be junk data - nothing like that in the bigger files, and seems inconsistent.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-10-27T23:33:14+00:00
- Post Title: Metal Wolf Chaos *.msg files

edit - here is a better one to parse all files   

```
{
  uint strings;
  uint un_1; // 0
  uint un_2; // 0
  uint un_3; // 0
};

struct data
{
  int id;
  uint offset;
};

head hdr;

local int num;
local int i;
local string str;

num = (ReadUInt(FTell()+4)-16) / sizeof(data);

data body[num];

for(i=0;i<num;++i)
{
  if(body[i].id > 0 && body[i].offset != 0)
  {
    str = ReadString(body[i].offset);
    Printf("%08X - %s¥n", body[i].id, StringToWString(str, CHARSET_JAPANESE));
  }
}

```


gives

> 00072BF0 - 赤き箱を探し出し
>
> 00072BF1 - 全て打ち砕くべし
>
> 00072C04 - よくぞ成し遂げた

with m037.msg
## Post #3
- Username: SonofUgly
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Feb 25, 2012 9:43 pm
- Post datetime: 2016-10-28T08:53:03+00:00
- Post Title: Metal Wolf Chaos *.msg files

Awesome, thanks. 
Anyway to run it in reverse?

Also turns out 1 (just 1... of course) file is slightly different, and the output is missing strings. File: [http://www.mediafire.com/file/kf2zcxoatfq7nns/menu.msg](http://www.mediafire.com/file/kf2zcxoatfq7nns/menu.msg) and output: [http://pastebin.com/AkXA9PLx](http://pastebin.com/AkXA9PLx).
Didn't go through it thoroughly, but I can see that at least "000702EF - GAME 2" is missing. And I was wrong about the first 8 bytes being byteswapped.
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-10-28T22:08:58+00:00
- Post Title: Metal Wolf Chaos *.msg files

> Reply from SonofUgly
>
> Also turns out 1 (just 1... of course) file is slightly different, and the output is missing strings. 

Didn't go through it thoroughly, but I can see that at least "000702EF - GAME 2" is missing

yeah this file is a problem. there are no flags to control how large the 'data info' structure should be.

here is an update - uncomment the #define on line 1 to for menu.msg

```

struct head
{
  uint strings;
  uint un_1; // 0
  uint un_2; // 0
  uint un_3; // 0
};

struct data
{
  int id;
  uint offset;

#ifdef MENU_MSG
  uint unknown;
#endif
};

struct str
{
  string c;
};

head hdr;

local int num;
local int i;

num = (ReadUInt(FTell()+4)-16) / sizeof(data);

data body[num];

for(i=0;i<num;++i)
{
  if(body[i].offset != 0)
  {
    FSeek(body[i].offset);
    str cstr <bgcolor=0xffccee>;

    if(WStrlen(cstr.c)>0 || body[i].id > 0)
    {   
      Printf("%08X - %s\n", body[i].id, StringToWString(cstr.c, CHARSET_JAPANESE));
    }
  }
}

```
