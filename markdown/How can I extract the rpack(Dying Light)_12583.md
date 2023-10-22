## Post #1
- Username: yolaeng
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 08, 2015 12:14 am
- Post datetime: 2015-02-07T17:23:12+00:00
- Post Title: How can I extract the rpack?(Dying Light)

Hi there!
I can't speak English well
So I need you to understand , so writing a translator

I'm trying to create a localized patch dying light . (ENG -> KOR)
Our translation team has already had translated into korean language
but, rpack can not be extracted .
So it is necessary to extract tools or source

Who can give me information?
about extract tools or source..
Please give me some information T.T

And I want to make foreign friends!
I 'm now studying English while the translations
Very funny.
See you again, Pal!
## Post #2
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2015-02-09T06:54:54+00:00
- Post Title: How can I extract the rpack?(Dying Light)

여기는 서로 아는 정보를 공유하면서 연구해나가는 공간입니다.

i think this will help [http://svn.gib.me/public/chrome/trunk/](http://svn.gib.me/public/chrome/trunk/)
## Post #3
- Username: dubh
- Rank: n00b
- Number of posts: 13
- Joined date: Mon May 23, 2011 4:34 pm
- Post datetime: 2015-02-12T04:07:17+00:00
- Post Title: How can I extract the rpack?(Dying Light)

> Reply from MiRiKan
>
> 여기는 서로 아는 정보를 공유하면서 연구해나가는 공간입니다.

i think this will help http://svn.gib.me/public/chrome/trunk/
That's for Dead Island.
## Post #4
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2015-02-13T14:29:38+00:00
- Post Title: How can I extract the rpack?(Dying Light)

> Reply from dubh
>
> MiRiKan wrote:여기는 서로 아는 정보를 공유하면서 연구해나가는 공간입니다.

i think this will help http://svn.gib.me/public/chrome/trunk/
That's for Dead Island.

yeah, but almost same base.
## Post #5
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2015-02-14T02:36:43+00:00
- Post Title: How can I extract the rpack?(Dying Light)

```
//--- 010 Editor v6.0.1 Binary Template
//
// File: Dying Light .rpack files
// Author:MiRiKan, refer to Gibbed
// Revision:0.1
// Purpose:To decrypt Dying Light .rpack files
//--------------------------------------
LittleEndian();

local uint i, pos, pos2;

char header[3] <open=suppress>;
char identity;
uint version;
uint flages;
uint dataCount;
uint typeCount;
uint nameCount;
uint nameDataSize;
uint entryCount;
uint Alignment;

struct typeHeaders{
    for (i = 0; i < typeCount; i++){
        struct Deserialize1{
            uint Flage;
            uint Offset;
            uint UncompressedSize;
            uint CompressedSize;
            uint16 ResourceCount;
            uint16 unk;
        }F;
    }
}HEADER;

struct dataHeaders{
    for (i = 0; i < dataCount; i++){
        struct Deserialize2{
            uint Flags;
            uint Offset; //???? it was offset in chrome engine 5. But it looks something's changed now.
            uint UncompressedSize;
            uint CompressedSize;
        }D;
    }
}DATA;

struct entryHeaders{
    for (i = 0; i < entryCount; i++){
        struct Deserialize3{
            uint Flags;
            uint FirstNameIndex;
            uint FirstDataIndex;
        }D;
    }
}ENTRY;

pos = FTell();
struct Names{
    for (i = 0; i < nameCount; i++){
        struct FileName{
            uint Off;
            pos2 = FTell();
            FSeek(pos + (nameCount * 4) + Off);
            string name <open=suppress>;
            FSeek(pos2);
        }FN;
    }
}NAME;

FSeek(pos + (nameCount * 8));
```


refer to Gibbed, But something different.
Anyone know?
