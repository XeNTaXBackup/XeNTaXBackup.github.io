## Post #1
- Username: thebreakdownprocess
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 18, 2015 5:52 am
- Post datetime: 2015-01-23T14:21:56+00:00
- Post Title: Tree of Savior .ies datatable (GE IES Reader not working)

I've attached a copy of an example .ies datatable file for the game. The game is the same developer for Granado Espada and they're using a similar game engine so I was hoping I could use the GE IES Reader that was developed elsewhere in these forums, but to no avail 

Is there a program I can use to view these files? VB? C++? I'm willing to research coding languages if someone would just steer me in the right direction. Any help is appreciated. Thank you in advance!
[statbase_weapon.rar](https://xentaxbackup.github.io/file/8550_statbase_weapon.rar)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-23T18:40:58+00:00
- Post Title: Tree of Savior .ies datatable (GE IES Reader not working)

i answered a pm about this the other day

here is a rough parser. basically

the strings characters are scrambled with an xor key (0x1)
the table structure is defined first
the table contents are defined at the end (packed in the format of structure)

i'm sure there are other ies parsers out there

** REMOVED OLD CODE. SEE BELOW FOR UPDATED VERSION **

edit

see this thread - [viewtopic.php?p=34555#p34555](http://forum.xentax.com/viewtopic.php?p=34555#p34555)
## Post #3
- Username: thebreakdownprocess
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 18, 2015 5:52 am
- Post datetime: 2015-01-24T01:03:39+00:00
- Post Title: Tree of Savior .ies datatable (GE IES Reader not working)

Sorry I'm not sure if I quite understand. Is this VB code? If so how would I even run this code? What program would I use?
## Post #4
- Username: mumphster
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 17, 2015 7:46 am
- Post datetime: 2015-01-24T02:29:47+00:00
- Post Title: Tree of Savior .ies datatable (GE IES Reader not working)

Hey thanks for the template, I've been using this to write a little parser in Go. Some advice for other people: sometimes there isnt a row/format count (check out camera.ies). Threw me for a loop when writing this generic parser.
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-24T20:50:32+00:00
- Post Title: Tree of Savior .ies datatable (GE IES Reader not working)

> Reply from thebreakdownprocess
>
> Sorry I'm not sure if I quite understand. Is this VB code? If so how would I even run this code? What program would I use?

it's a 010 editor binary template. there is a comment at the start of the script showing this. i also have a link to prelen.bt in my signature.

> Reply from mumphster
>
> Hey thanks for the template, I've been using this to write a little parser in Go. Some advice for other people: sometimes there isnt a row/format count (check out camera.ies). Threw me for a loop when writing this generic parser.

i only have a few samples - are all the strings scrambling the same way?
also, some older ies files only have a 64 byte filename header, these samples are 128 bytes
## Post #6
- Username: mumphster
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 17, 2015 7:46 am
- Post datetime: 2015-01-24T21:44:50+00:00
- Post Title: Tree of Savior .ies datatable (GE IES Reader not working)

Ya I think they changed it up in tree of savior, theres also no distinction between int/string types for data.. as far as i can tell at least
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-25T01:21:25+00:00
- Post Title: Tree of Savior .ies datatable (GE IES Reader not working)

> Reply from mumphster
>
> Ya I think they changed it up in tree of savior, theres also no distinction between int/string types for data.. as far as i can tell at least

there was in the previous version - i linked to that thread above.

anyway, here is an updated version which parses all samples i have:

```
//--- 010 Editor v5.0 Binary Template
//
// File:        IESv2.bt
// Author:      WRS
// Revision:    2
// Purpose:     IES Database Parser
//--------------------------------------

#include "prelen.bt"

#define ENABLE_IES_WARNINGS

////////////////////////////////////////////////////////////

struct str_custom(int type)
{
  str _str(type);
};

typedef str_custom cstr <read=GetCStrValue>;

string GetCStrValue(cstr &t)
{
  local string result = "";
  local int i = 0;
  while(i<t._str.len) {
    if(t._str.val[i]==0) break;
    result += (char)(t._str.val[i] ^ 0x1);
    ++i;
  }

  return result;
}

////////////////////////////////////////////////////////////
// File header
////////////////////////////////////////////////////////////

struct HEADER
{
    str Filename(128);
    
    uint int_val_1;
    uint offset_hint_a; // subtract from file_size to get ptr
    uint offset_hint_b;
    uint file_size;
}
hdr;

#ifdef ENABLE_IES_WARNINGS
Assert( hdr.file_size == FileSize() );
#endif

////////////////////////////////////////////////////////////
// Data info
////////////////////////////////////////////////////////////

struct INFO
{
    ushort short_val_1; // always 1?
    ushort Rows; // number of rows
    ushort Columns; // total number of int and string columns
    ushort ColInt; // cols which are ints
    ushort ColString; // cols which are strings
}
info;

#ifdef ENABLE_IES_WARNINGS
if(info.ColString + info.ColInt != info.Columns)
{
    Warning("Wrong number of column type descriptors");
}
#endif

local uint OffsetColumns = hdr.file_size - (hdr.offset_hint_a+hdr.offset_hint_b);
local uint OffsetRows = hdr.file_size - hdr.offset_hint_b;
FSeek(OffsetColumns);

////////////////////////////////////////////////////////////
// Column format
////////////////////////////////////////////////////////////

enum<ushort> FmtType
{
    TYPE_INT = 0,
    TYPE_STR = 1
};

struct
{
    local int count_int = 0;
    local int count_str = 0;

    Printf("%i Columns:\n", info.Columns);
    
    struct Col
    {
        //ushort unknown;
        cstr Name1(64);
        cstr Name2(64);
        FmtType Type;
        byte unknown[6];
    
        switch(Type)
        {
            case TYPE_INT: ++count_int; break;
            case TYPE_STR: ++count_str; break;
#ifdef ENABLE_IES_WARNINGS
            default: Warning("Unknown column type");
#endif
        }
    
        Printf("[%s] %s\n", EnumToString(Type), GetCStrValue(Name1));
    
    } col[info.Columns] <optimize=false>;
    
#ifdef ENABLE_IES_WARNINGS
    Assert(count_int == info.ColInt);
    Assert(count_str == info.ColString);
#endif
}
ColumnList;

#ifdef ENABLE_IES_WARNINGS
Assert(FTell() == OffsetRows);
#endif

////////////////////////////////////////////////////////////
// Rows
// NOTE: Strings are sometimes scrambled differently from the xor
////////////////////////////////////////////////////////////

struct
{
    struct Row
    {
        int row_index;
        cstr optional_str(plen16);
    
        int IntPool[info.ColInt];
        cstr StringPool(plen16)[info.ColString] <optimize=false>;
        
        // Not sure why these are there
        FSkip(info.ColString);
    } row[info.Rows] <optimize=false>;
}
RowList;

////////////////////////////////////////////////////////////
// End of file
////////////////////////////////////////////////////////////

#ifdef ENABLE_IES_WARNINGS
Assert(FEof());
#endif

```
## Post #8
- Username: thebreakdownprocess
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 18, 2015 5:52 am
- Post datetime: 2015-01-25T03:02:23+00:00
- Post Title: Tree of Savior .ies datatable (GE IES Reader not working)

> there was in the previous version - i linked to that thread above.
>
> 
>
> anyway, here is an updated version which parses all samples i have:

I received the following error while using the template you provided. Also when I used the template on another .ies file, it came up with 217 in 'struct ColumnList' but only 107 values in 'struct Row row[0]'. The row values don't match up to the column values?
[error.jpg](https://xentaxbackup.github.io/file/8558_error.jpg)
## Post #9
- Username: thebreakdownprocess
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 18, 2015 5:52 am
- Post datetime: 2015-01-25T03:04:31+00:00
- Post Title: Tree of Savior .ies datatable (GE IES Reader not working)

I attached the file I received an error on.
[item.zip](https://xentaxbackup.github.io/file/8559_item.zip)
## Post #10
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-25T15:28:01+00:00
- Post Title: Tree of Savior .ies datatable (GE IES Reader not working)

> Reply from thebreakdownprocess
>
> I attached the file I received an error on.

change this line:

> #define ENABLE_IES_WARNINGS
to 

```
//#define ENABLE_IES_WARNINGS
```


and the row count does not have to match the col count - it works like a spreadsheet
## Post #11
- Username: thebreakdownprocess
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 18, 2015 5:52 am
- Post datetime: 2015-01-25T21:19:59+00:00
- Post Title: Tree of Savior .ies datatable (GE IES Reader not working)

> Reply from WRS
>
> the row count does not have to match the col count - it works like a spreadsheet

Sorry what I meant was the information doesn't really match up with the columns. The rows in the columns for sound files don't match the rows where the sound files actually are in the data. See attached to see what I mean. This is when I line up the columns and rows as is. Is there a way to figure out which row is supposed to go to which column?
[excel.jpg](https://xentaxbackup.github.io/file/8564_excel.jpg)
## Post #12
- Username: mumphster
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 17, 2015 7:46 am
- Post datetime: 2015-01-25T21:29:33+00:00
- Post Title: Tree of Savior .ies datatable (GE IES Reader not working)

Looks like the file is missing taking into account the order field on the nodes. It was in the last script so it might have just slipped your mind haha.

Went ahead and finished up my golang parser

```
...

map[ClassID:0 ClassName:All_of_Fury FileName:SFA_All_of_fury.mp3 Composer:S.F.A Copyrights:x Staff:NO]                              
map[ClassName:Chariots_of_Fire FileName:SFA_Chariots_of_fire.mp3 Composer:S.F.A Copyrights:x Staff:NO ClassID:0]                    
map[FileName:SFA_D_Lejano.mp3 Composer:S.F.A Copyrights:x Staff:NO ClassID:0 ClassName:D_Lejano]                                    
map[ClassID:0 ClassName:Dejame_Volver FileName:SFA_Dejame_Volver.mp3 Composer:S.F.A Copyrights:x Staff:NO]                          
map[ClassName:Divine_Destiny FileName:SFA_Divine_Destiny.mp3 Composer:S.F.A Copyrights:x Staff:NO ClassID:0]                        
map[Copyrights:x Staff:NO ClassID:0 ClassName:Double_Trouble FileName:SFA_Double_Trouble.mp3 Composer:S.F.A]                        
map[ClassName:Eleminuete FileName:SFA_Eleminuete.mp3 Composer:S.F.A Copyrights:x Staff:NO ClassID:0]                                
map[Composer:S.F.A Copyrights:x Staff:NO ClassID:0 ClassName:Epic FileName:SFA_Epic.mp3]                                            
map[Copyrights:x Staff:NO ClassID:0 ClassName:Escarceo_de_Onda FileName:SFA_Escarceo_de_Onda.mp3 Composer:S.F.A]                    
map[ClassID:0 ClassName:Groove_of_the_Sea FileName:SFA_Groove_of_the_Sea.mp3 Composer:S.F.A Copyrights:x Staff:NO]                  
map[FileName:SFA_Journey_in_Heaven.mp3 Composer:S.F.A Copyrights:x Staff:NO ClassID:0 ClassName:Journey_in_Heaven]                  
map[ClassName:Justice_for_you FileName:SFA_Justice_for_you.mp3 Composer:S.F.A Copyrights:x Staff:NO ClassID:0]                      
map[Copyrights:x Staff:NO ClassID:0 ClassName:Klasika FileName:SFA_Klasika.mp3 Composer:S.F.A]                                      
map[ClassID:0 ClassName:La_Valle_della_Morte FileName:SFA_La_Valle_della_Morte.mp3 Composer:S.F.A Copyrights:x Staff:NO]            
map[ClassID:0 ClassName:Outcry FileName:SFA_Outcry.mp3 Composer:S.F.A Copyrights:x Staff:NO]                                        
map[Composer:S.F.A Copyrights:x Staff:NO ClassID:0 ClassName:Rozee FileName:SFA_Rozee.mp3]                                          
map[Copyrights:x Staff:NO ClassID:0 ClassName:Sad_Feeling FileName:SFA_Sad_feelings.mp3 Composer:S.F.A]                             
map[ClassName:The_Entrance_of_Glory FileName:SFA_The_Entrance_of_Glory.mp3 Composer:S.F.A Copyrights:x Staff:NO ClassID:0]          
map[Copyrights:x Staff:NO ClassID:0 ClassName:The_Kingdom_Overcomes FileName:SFA_The_Kingdom_Overcomes.mp3 Composer:S.F.A]          
map[ClassID:0 ClassName:The_Last_of_Chaos FileName:SFA_The_Last_of_Chaos.mp3 Composer:S.F.A Copyrights:x Staff:NO]                  
map[ClassID:0 ClassName:The_Wisdom_of_Crowds FileName:SFA_The_Wisdom_of_Crowds.mp3 Composer:S.F.A Copyrights:x Staff:NO]            
map[ClassID:0 ClassName:Uncontroversial FileName:SFA_Uncontroversial.mp3 Composer:S.F.A Copyrights:x Staff:NO]                      

...


```


woohoo! thanks again for all the hard work. 

All my code can be found at [https://github.com/Ell/tostools](https://github.com/Ell/tostools) and ill be sure to credit you WRS
