## Post #1
- Username: xvi3r
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 16, 2016 8:30 am
- Post datetime: 2016-02-22T15:18:15+00:00
- Post Title: BLJM61257 Sengoku Musou 4 II PS3 English Translation Help

Hi.

I want to do a fan made translation of this game

I want it because the english version NPUB31751_SAMURAI_WARRIORS_4-II doesnt have the RETAIL ISO version and i cant turn it to
ISO (to save space in my ps3 hdd and i dont have money for another HDD for my ps3)

I opened the ISO and i found:

LINKDATA_1ST.BIN
LINKDATA_2ND.BIN

and go on...mostly *.BIN files in varios sizes (3gb bigger one).

how or which tool do i need to open those files so i can see the pics and the TEXTs in order to start the translation in english?

hope someone can aid me.

Thank you.

BTW: I got those files in ENGLISH but those are in the PSN PKG version not retail version as the JP version and as far as i know they are not compatible.

Example (BIN FILE): [https://mega.nz/#!5QclFYwJ!7aCu0nkyA1DI ... GjHzROOaEQ](https://mega.nz/#!5QclFYwJ!7aCu0nkyA1DIIcAsK0VdJhFichW6VUEeJGjHzROOaEQ)
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-23T16:27:00+00:00
- Post Title: BLJM61257 Sengoku Musou 4 II PS3 English Translation Help

The file is zlib compressed. You can use offzip to extract some of the data.

Here are the structs:

```
{
       unsigned int unknown;//Always zero
       unsigned int fileOffset;//Multiply this by 0x800 (fileAlignment) to get the file offset
       unsigned int compressedSize;//Not really, see two 32-bit ints @fileOffset for real sizes.
       unsigned int uncompressedSize;//Not checked
};

struct Bin
{
        unsigned int magic;//0x00102A49
        unsigned int numFiles;
        unsigned int fileAlignment;
        unsigned int unknown;
        BinEntry[numFiles];
};

```
## Post #3
- Username: xvi3r
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 16, 2016 8:30 am
- Post datetime: 2016-03-03T01:30:05+00:00
- Post Title: BLJM61257 Sengoku Musou 4 II PS3 English Translation Help

> Reply from Gh0stBlade
>
> The file is zlib compressed. You can use offzip to extract some of the data.

Here are the structs:
Code: Select allstruct BinEntry
{
       unsigned int unknown;//Always zero
       unsigned int fileOffset;//Multiply this by 0x800 (fileAlignment) to get the file offset
       unsigned int compressedSize;//Not really, see two 32-bit ints @fileOffset for real sizes.
       unsigned int uncompressedSize;//Not checked
};

struct Bin
{
        unsigned int magic;//0x00102A49
        unsigned int numFiles;
        unsigned int fileAlignment;
        unsigned int unknown;
        BinEntry[numFiles];
};

thank you!, but what should i do with that structure now?

put it where? do i need to create a exe o a BAT file with that command structure?

thank you
## Post #4
- Username: xvi3r
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-03-04T11:39:52+00:00
- Post Title: BLJM61257 Sengoku Musou 4 II PS3 English Translation Help

> Reply from xvi3r
>
> Gh0stBlade wrote:The file is zlib compressed. You can use offzip to extract some of the data.

Here are the structs:
Code: Select allstruct BinEntry
{
       unsigned int unknown;//Always zero
       unsigned int fileOffset;//Multiply this by 0x800 (fileAlignment) to get the file offset
       unsigned int compressedSize;//Not really, see two 32-bit ints @fileOffset for real sizes.
       unsigned int uncompressedSize;//Not checked
};

struct Bin
{
        unsigned int magic;//0x00102A49
        unsigned int numFiles;
        unsigned int fileAlignment;
        unsigned int unknown;
        BinEntry[numFiles];
};


thank you!, but what should i do with that structure now?

put it where? do i need to create a exe o a BAT file with that command structure?

thank you

It's basically the file format, so someone could easily write an unpacker for those files. Compression used is Zlib.
## Post #5
- Username: xvi3r
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 16, 2016 8:30 am
- Post datetime: 2016-03-04T19:59:46+00:00
- Post Title: BLJM61257 Sengoku Musou 4 II PS3 English Translation Help

> Reply from Gh0stBlade
>
> xvi3r wrote:Gh0stBlade wrote:The file is zlib compressed. You can use offzip to extract some of the data.

Here are the structs:
Code: Select allstruct BinEntry
{
       unsigned int unknown;//Always zero
       unsigned int fileOffset;//Multiply this by 0x800 (fileAlignment) to get the file offset
       unsigned int compressedSize;//Not really, see two 32-bit ints @fileOffset for real sizes.
       unsigned int uncompressedSize;//Not checked
};

struct Bin
{
        unsigned int magic;//0x00102A49
        unsigned int numFiles;
        unsigned int fileAlignment;
        unsigned int unknown;
        BinEntry[numFiles];
};


thank you!, but what should i do with that structure now?

put it where? do i need to create a exe o a BAT file with that command structure?

thank you

It's basically the file format, so someone could easily write an unpacker for those files. Compression used is Zlib.

Hi Gh0stBlade.

First of all, im thankfull for the time you took for answer me.

I still dont have a clue for what to do with that code. Put it where? how can i built an unpacker? i dont know how to search. Can you throw me a bone please?   

Thank you again
