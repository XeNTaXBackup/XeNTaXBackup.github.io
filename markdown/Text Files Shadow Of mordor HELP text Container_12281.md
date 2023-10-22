## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-11-27T09:51:00+00:00
- Post Title: Text Files Shadow Of mordor *HELP* text Container

Can anyone help please with this format ??

Download (rest in signature add before (dropbox):

```
38234344/stringSoM.rar
```


This is what i have so far... I cannot find offset 

```

local uint x;

char sign[4];
uint version;
uint headsize;
uint entry;
uint64 textSize; // must be *2 coz of unicode
byte bbb[8];

for (x=0;x<entry;x++) {

 struct Entry {
    //uint ID;
    //uint Offset;

    ushort id1;    //???
    ushort id2;   //????
    ushort of1;   //????
    ushort of2;   //????

 }data;

}

```
## Post #2
- Username: InKviZ
- Rank: advanced
- Number of posts: 51
- Joined date: Mon Sep 29, 2014 12:57 am
- Post datetime: 2014-11-27T14:43:43+00:00
- Post Title: Text Files Shadow Of mordor *HELP* text Container

And where is the text ??? And share unpack and pack archives.
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-11-27T16:42:43+00:00
- Post Title: Text Files Shadow Of mordor *HELP* text Container

> Reply from InKviZ
>
> And where is the text ??? And share unpack and pack archives.

If you want repacker for PC you won't find one. This is from X360 version, however only different is endian...
## Post #4
- Username: InKviZ
- Rank: advanced
- Number of posts: 51
- Joined date: Mon Sep 29, 2014 12:57 am
- Post datetime: 2014-11-27T18:14:43+00:00
- Post Title: Text Files Shadow Of mordor *HELP* text Container

If you want repacker for PC you won't find one. This is from X360 version, however only different is endian...[/quote]
This is bad ....
## Post #5
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-11-29T07:56:26+00:00
- Post Title: Text Files Shadow Of mordor *HELP* text Container

anyone please ? I cannot figure it out
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-11-30T17:59:25+00:00
- Post Title: Text Files Shadow Of mordor *HELP* text Container

those widestrings are padded to 4 byte blocks

but the string count isn't in the header - the 32180 is this entry count

english - there are 27414 strings
french - there are 23344 strings
russian - there are 14142 strings

there are some html like colours
## Post #7
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-12-01T06:19:45+00:00
- Post Title: Text Files Shadow Of mordor *HELP* text Container

> Reply from WRS
>
> those widestrings are padded to 4 byte blocks

but the string count isn't in the header - the 32180 is this entry count

english - there are 27414 strings
french - there are 23344 strings
russian - there are 14142 strings

there are some html like colours

thx but not sure if i understand  From my script as you can see that TextSize is size of text block * 2. It is perfect in every language file. However i have try to repack this file and it is working but once you make strings longer text is broken in game. There must be something im missing.
## Post #8
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-12-01T09:07:14+00:00
- Post Title: Text Files Shadow Of mordor *HELP* text Container

My latest wersion but i dont think this is right:

```
//--- 010 Editor v5.0.2 Binary Template
//
// File:
// Author: michalss
// Revision: 1.5
// Purpose: Shadow of Mordor TextFiles
//--------------------------------------
BigEndian();

local uint x,padding,dCounter;
local string text;

char sign[4];
uint version;
uint headsize;
uint entry;
uint64 textSize; // must be *2 coz of unicode
uint64 unk;


struct DONTKNOW {
    for (x=0;x<entry;x++) {

        struct Entry {
   
            uint dummy;    
            uint crc;

        }data;

   }
}n;

dCounter = (textSize*2)+(entry*2);

struct TextEntry {
do {

 struct Text {
         
    text=ReadWString(FTell());
    char TextF[Strlen(text)*2];    
    padding=ReadUInt(FTell());
    if (padding==0) {
        byte padding[4];
    }else{       
        byte padding[2];
    }
 }data;


} while (FTell()<=FileSize()-1);
} E;
//Printf("Counter %i\n",dCounter);
```
## Post #9
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2014-12-29T02:34:23+00:00
- Post Title: Text Files Shadow Of mordor *HELP* text Container

```
//--- 010 Editor ver 6.0 mordor PC
//
// File: string.strdb
// Author: MiRiKan updated, michalss
// Revision: 1.7
// Purpose: Shadow of Mordor text script
//--------------------------------------
local uint x,padding,dCounter;
local uint ftell;
char identity[4]; //SKDB
uint dummy1; 
uint SizeOfHeader;
uint PointerOfStrings;
uint64 textSize;
uint64 dummy2;
struct Unknown {
    for (x=0;x<PointerOfStrings;x++) {
        struct UNKNOWN {
            uint unknown1;    
            uint unknown2;
        }data;
   }
}DATA;
dCounter = (textSize*2)+(PointerOfStrings*2);
struct Strings {
     while (FTell()<=FileSize()-1){
        struct Text {
            wstring text;
            ftell = FTell();
            FSeek(ftell-2);
            padding=ReadUInt(FTell());
            if (padding==0) {
                byte padding[4];
            }else{
                byte padding[2];
            } 
        }strings;
    };
}TEXT;
```


I changed little things for PC.
and i think your file will need "BigEndian();"
## Post #10
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-12-29T10:00:39+00:00
- Post Title: Text Files Shadow Of mordor *HELP* text Container

Problem is that template is not correct  You just copied over, not helpful pretty much  Need to understand this unk uints!
## Post #11
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2014-12-30T03:14:18+00:00
- Post Title: Text Files Shadow Of mordor *HELP* text Container

> Reply from michalss
>
> Problem is that template is not correct  You just copied over, not helpful pretty much  Need to understand this unk uints!

Yes, you are right.
but i really don't know what it is.
maybe it might be some pointers for texts. i'll think and think again

```
    for (x=0;x<PointerOfStrings;x++) {
        struct Point {
            uint unk1; // maybe pointer
            uint ID; 
        }data;

   }
}D;
```
## Post #12
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-12-30T08:41:14+00:00
- Post Title: Text Files Shadow Of mordor *HELP* text Container

OK sorted with little help of my friend evin
## Post #13
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2014-12-30T09:18:29+00:00
- Post Title: Text Files Shadow Of mordor *HELP* text Container

Hum. Japanese texts are 14299. but pointers are 32269.
and English texts are 27413. but pointers are 32179.
...So i think this pointers have so many dummys in there. 
also there is so many dummys in English texts! i found that "Level" text or some strings about FPS game - which were in the F.E.A.R game, perhaps.
i can not separate dummy data from this strings...
## Post #14
- Username: MiRiKan
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-12-30T10:17:55+00:00
- Post Title: Text Files Shadow Of mordor *HELP* text Container

Here you GO  easy..  Goona do repacker soon

```
//--- 010 Editor ver 5.2 mordor X360
//
// File: string.strdb
// Author: michalss
// Revision: 2
// Purpose: Shadow of Mordor text script
//--------------------------------------

BigEndian();

local uint x,padding,dCounter;
local uint pos;

char identity[4]; 
uint version; 
uint SizeOfHeader;
uint countStrings;
uint Null1;
uint textSize;
uint Null2;

dCounter = SizeOfHeader + countStrings*8;

struct TextData {
    for (x=0;x<countStrings;x++) {
        struct StringsUni{
           uint TextID;
           uint TextStartPos; 
           pos = FTell();
           FSeek(TextStartPos*2+dCounter); 
           wstring text;  
           FSeek(pos); 
        }data;
   }
}DATA;
```
## Post #15
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2014-12-31T01:36:29+00:00
- Post Title: Text Files Shadow Of mordor *HELP* text Container

> Reply from michalss
>
> Here you GO  easy..  Goona do repacker soon
Code: Select all//--------------------------------------
//--- 010 Editor ver 5.2 mordor X360
//
// File: string.strdb
// Author: michalss
// Revision: 2
// Purpose: Shadow of Mordor text script
//--------------------------------------

BigEndian();

local uint x,padding,dCounter;
local uint pos;

char identity[4]; 
uint version; 
uint SizeOfHeader;
uint countStrings;
uint Null1;
uint textSize;
uint Null2;

dCounter = SizeOfHeader + countStrings*8;

struct TextData {
    for (x=0;x<countStrings;x++) {
        struct StringsUni{
           uint TextID;
           uint TextStartPos; 
           pos = FTell();
           FSeek(TextStartPos*2+dCounter); 
           wstring text;  
           FSeek(pos); 
        }data;
   }
}DATA;

WOW, i was just missed cause i didn't know where end of header is. you are amazing
Thanks
## Post #16
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-12-31T12:08:29+00:00
- Post Title: Re: Text Files Shadow Of mordor *HELP* text Container

ok now im working on proper unpacker and packer...
## Post #17
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2014-12-31T14:59:10+00:00
- Post Title: Re: Text Files Shadow Of mordor *HELP* text Container

i made packer. it use .xlsx file.
and it will work for XBOX 360 and PC.
it'll create .strdb file with .xlsx
before use this, you have to do it:
1. this program will load "Mordor_texts.xlsx" file. if you have difference name of .xlsx file, just edit run.bat or drag & drop to Mordor_Text_packer1.0.exe
2. .xlsx file form have to same like sample file. AND DO NOT CHANGE first row texts.

feel free 

```
https://mega.co.nz/#!DhxVHCga!7FNiMlNiaRBKkZApDf-Ln8z2W_B-yPq2zTq9FX9G95w
```


version log
1.1
some minor bug fixed
1.0
## Post #18
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-12-31T16:00:28+00:00
- Post Title: Re: Text Files Shadow Of mordor *HELP* text Container

No problem i made my own  using TXT file also crearing *.strdb without original file. Very quick and simple..... Also tested in game and it works perfectly
## Post #19
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2015-01-01T08:15:14+00:00
- Post Title: Re: Text Files Shadow Of mordor *HELP* text Container

Great 
in conclusion,
this is extracted texts .xlsx file: 

```
https://mega.co.nz/#!ekAEHIDY!dMFAkn34WXb0sGFKTxQHa3jlwFbHrIfVfUXoEekM_PI
```

extracted at 2015.1.1.

if game updated some texts, you can just add strings with ID and text.
010 Editor will best for it.

```
//--- 010 Editor ver 6 Mordor PC
// if your file formed for xbox360, just add at first line this: BigEndian();
// File: string.strdb
// Author: little fix by mirikan, original made by michalss
// Revision: 2.2
// Purpose: Shadow of Mordor text script
//--------------------------------------
local uint x,padding,dCounter;
local uint pos;
char identity[4];
uint version; 
uint SizeOfHeader;
uint CountStrings;
uint dummy1;
uint textSize;
uint dummy2;

dCounter = (CountStrings*8) + (SizeOfHeader);

struct TextData {
    for (x=0;x<CountStrings;x++) {
        struct StringUniCode {
            uint TextID;
            uint TextPos;
            pos = FTell();
            FSeek(TextPos*2+dCounter);
            wstring Text [b]<open=suppress>[/b]; //it will help you whan you want extract texts via 010 Editor
            FSeek(pos);
        }data;
   }
}DATA;
```


<open=suppress> will help you whan you want extract texts via 010 Editor. just use this Templates and go Template Result -> Right mouse -> Expand All Nodes -> Right mouse again -> Export or Copy, as you like!

this is text repacker. easy to use 
Please read text file README.txt before run it.

```
https://mega.co.nz/#!SgQiWaxL!UddGRmjjCY2ftroPkrZ5d_kNMVPAxg0s6m2EMGPS374
```

(sorry again! it had been problem with max-length cause c#. but fixed)
(sorry it changed 1.3 version. and tested on game)

Thanks to michalss!
Happy new year XeNTaX guys!
## Post #20
- Username: VahapZTL
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 29, 2015 7:18 pm
- Post datetime: 2015-10-02T21:23:18+00:00
- Post Title: Re: Text Files Shadow Of mordor *HELP* text Container

Hi. I am trying to get the Shadow of Mordor localization files to translate into my language but I dont know how to use the 010 editor. Can you please explain me step by step how to use it? Thanks for your help
## Post #21
- Username: gula
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 14, 2014 8:17 pm
- Post datetime: 2015-11-15T11:19:23+00:00
- Post Title: Re: Text Files Shadow Of mordor *HELP* text Container

> Reply from VahapZTL
>
> Hi. I am trying to get the Shadow of Mordor localization files to translate into my language but I dont know how to use the 010 editor. Can you please explain me step by step how to use it? Thanks for your help

i'm repack the text. I have texttool.

[http://www75.zippyshare.com/v/2QQo83dN/file.html](http://www75.zippyshare.com/v/2QQo83dN/file.html)
## Post #22
- Username: dvoika
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Nov 08, 2014 4:19 am
- Post datetime: 2016-09-11T10:06:08+00:00
- Post Title: Re: Text Files Shadow Of mordor *HELP* text Container

hello pls have anyone this texttool, Mordor_Text_packer1.0.exe, unpacker and packer...anythinks...tnx

how i remake string.strdb(PC czech language) on ps3 string.strdb
tnx
## Post #23
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2017-04-21T21:02:21+00:00
- Post Title: Re: Text Files Shadow Of mordor *HELP* text Container

Link is dead. Please update v1.3 link.

> Reply from MiRiKan
>
> Great 
in conclusion,
this is extracted texts .xlsx file: 
Code: Select allhttps://mega.co.nz/#!ekAEHIDY!dMFAkn34WXb0sGFKTxQHa3jlwFbHrIfVfUXoEekM_PI
extracted at 2015.1.1.

if game updated some texts, you can just add strings with ID and text.
010 Editor will best for it.
Code: Select all//--------------------------------------
//--- 010 Editor ver 6 Mordor PC
// if your file formed for xbox360, just add at first line this: BigEndian();
// File: string.strdb
// Author: little fix by mirikan, original made by michalss
// Revision: 2.2
// Purpose: Shadow of Mordor text script
//--------------------------------------
local uint x,padding,dCounter;
local uint pos;
char identity[4];
uint version; 
uint SizeOfHeader;
uint CountStrings;
uint dummy1;
uint textSize;
uint dummy2;

dCounter = (CountStrings*8) + (SizeOfHeader);

struct TextData {
    for (x=0;x<CountStrings;x++) {
        struct StringUniCode {
            uint TextID;
            uint TextPos;
            pos = FTell();
            FSeek(TextPos*2+dCounter);
            wstring Text [b]<open=suppress>[/b]; //it will help you whan you want extract texts via 010 Editor
            FSeek(pos);
        }data;
   }
}DATA;

<open=suppress> will help you whan you want extract texts via 010 Editor. just use this Templates and go Template Result -> Right mouse -> Expand All Nodes -> Right mouse again -> Export or Copy, as you like!

this is text repacker. easy to use 
Please read text file README.txt before run it.
Code: Select allhttps://mega.co.nz/#!SgQiWaxL!UddGRmjjCY2ftroPkrZ5d_kNMVPAxg0s6m2EMGPS374
(sorry again! it had been problem with max-length cause c#. but fixed)
(sorry it changed 1.3 version. and tested on game)

Thanks to michalss!
Happy new year XeNTaX guys!
## Post #24
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2017-04-27T11:47:22+00:00
- Post Title: Re: Text Files Shadow Of mordor *HELP* text Container

Please update v1.3 link...
## Post #25
- Username: dvoika
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Nov 08, 2014 4:19 am
- Post datetime: 2017-05-05T15:42:24+00:00
- Post Title: Re: Text Files Shadow Of mordor *HELP* text Container

pls link
