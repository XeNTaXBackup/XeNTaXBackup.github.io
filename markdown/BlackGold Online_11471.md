## Post #1
- Username: geralex
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 09, 2012 5:50 pm
- Post datetime: 2014-04-30T13:58:45+00:00
- Post Title: BlackGold Online

Hello. Please, help. Do packer game resources this game?

Format: .package

Example:

```
struct PackHeader
{
	char MagicBytes[10];
	unsigned int FileCount;
	unsigned int DataStart;
	byte Filler00;
};

struct PackFile
{
	short DataLength;
	long long FileOffset;
	DWORD FileRawSize;
	DWORD FilePackSize;
	DWORD PackID;
	DWORD PackTime;
	byte Filler00;
	string FilePath;
	byte NullTerminate;
};
#pragma pack(pop)
```
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-04-30T18:34:50+00:00
- Post Title: BlackGold Online

And so? Where simple files or link for download client?
## Post #3
- Username: geralex
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 09, 2012 5:50 pm
- Post datetime: 2014-04-30T20:30:22+00:00
- Post Title: BlackGold Online

Link for sample files: [https://mega.co.nz/#!lRNVzJCJ!kcMGq7zgQ ... gLOqOEqi4k](https://mega.co.nz/#!lRNVzJCJ!kcMGq7zgQNJ2efKi5MwOYyBCmHvNA6yqOgLOqOEqi4k)
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-04-30T20:57:53+00:00
- Post Title: BlackGold Online

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "PCK0"
goto 0xA
get FILES long
get DATAOFFSET long
get DUMMY byte

for i = 0 < FILES
    get DUMMY1 short
    get OFFSET longlong
    get SIZE long
    get ZSIZE long
    get HASH long
    get DUMMY2 longlong
    get DUMMY3 byte
    get NAME string
    if ZSIZE == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-04-30T22:40:15+00:00
- Post Title: BlackGold Online

omg this games was developed by SnailGames, I have a friend work in this company oO so cool, I'll try contact him
## Post #6
- Username: geralex
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 09, 2012 5:50 pm
- Post datetime: 2014-05-01T07:49:38+00:00
- Post Title: BlackGold Online

> Reply from Ekey
>
> Code: Select all# BlackGold Online (PACKAGE format)
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "PCK0"
goto 0xA
get FILES long
get DATAOFFSET long
get DUMMY byte

for i = 0 < FILES
    get DUMMY1 short
    get OFFSET longlong
    get SIZE long
    get ZSIZE long
    get HASH long
    get DUMMY2 longlong
    get DUMMY3 byte
    get NAME string
    if ZSIZE == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i

I will try but this unpackage, how i can package for text.package ?
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-01T08:05:59+00:00
- Post Title: BlackGold Online

> Reply from geralex
>
> I will try but this unpackage, how i can package for text.package ?
This script for unpack. For pack read section 3 in QuickBMS readme.
