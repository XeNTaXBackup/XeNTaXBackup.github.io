## Post #1
- Username: Mattrio
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jan 31, 2016 9:57 pm
- Post datetime: 2016-02-05T20:14:32+00:00
- Post Title: EA STR string files

Hi everyone.

I'm a MySims games lover, and since it's been 6 years EA stopped doing games for the series, I'd like to do game mods. So I searched in MySims, MySims Kingdom and MySims Agents (Wii) files and these three games have their string files in *.str. It exists different str files, there is even str files in other MySims games but for different purposes (audio compression). Here, it looks like every string files such as language files are in str, and I can't manage to edit or read them correctly.

Luckily it exists a PC version of MySims, and in its files can be found language files in two formats: xml and str. XML are totally readable and editable. It exists their exact equivalent, so it can be easier to found a way to read str ones? I've attached two exact equivalent, I hope it will helps. 

Thanks
[mysimswii_languagefiles.zip](https://xentaxbackup.github.io/file/10427_mysimswii_languagefiles.zip)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-02-06T00:18:32+00:00
- Post Title: EA STR string files

this must already be documented......

aside from the xml flags, here is a rough template

```
{
  uint raw;

  struct
  {
    ubyte a;
    ubyte b;
    ubyte c;
    ubyte d;
  } _;
};

struct cstr
{
  uint len;
  string str;
};

enum <uint32> Lang
{
  ENG_US = 1,
};

Lang Language;
uint NodeCount;

struct Node
{
  meta metadata;
  cstr text;
};

Node Nodes[NodeCount] <optimize=false>;

```
## Post #3
- Username: Mattrio
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jan 31, 2016 9:57 pm
- Post datetime: 2016-02-06T12:28:53+00:00
- Post Title: EA STR string files

> Reply from WRS
>
> this must already be documented......

aside from the xml flags, here is a rough template
Code: Select allunion meta
{
  uint raw;

  struct
  {
    ubyte a;
    ubyte b;
    ubyte c;
    ubyte d;
  } _;
};

struct cstr
{
  uint len;
  string str;
};

enum <uint32> Lang
{
  ENG_US = 1,
};

Lang Language;
uint NodeCount;

struct Node
{
  meta metadata;
  cstr text;
};

Node Nodes[NodeCount] <optimize=false>;

Thank you, but I don't see how I could use this template? I tried with QuickBMS but I get the following error:

```
invalid command "union" or arguments -1 at line 1
```
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-02-06T14:17:24+00:00
- Post Title: EA STR string files

> Reply from Mattrio
>
> Thank you, but I don't see how I could use this template? I tried with QuickBMS but I get the following error:
Code: Select allinvalid command "union" or arguments -1 at line 1

sorry, this is a script for 010 editor.

note: there are no offsets in this file. you can resize strings and adjust the "size" value before the string. that's it!
## Post #5
- Username: Mattrio
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jan 31, 2016 9:57 pm
- Post datetime: 2016-02-20T13:22:16+00:00
- Post Title: EA STR string files

Thanks a lot!
