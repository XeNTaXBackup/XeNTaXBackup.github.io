## Post #1
- Username: Arcanjo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 11, 2014 4:27 am
- Post datetime: 2016-01-12T20:51:17+00:00
- Post Title: HELP!!!How to open files with extensions like this: 242BB29A

I'm trying to translate the game Dragon's Dogma for my language, but it has a problem, to extract the files I come across several others with these extensions "242BB29A" someone could tell me how to open them.

File to help test case. [http://upx.nz/4SdoOA](http://upx.nz/4SdoOA)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-12T22:41:56+00:00
- Post Title: HELP!!!How to open files with extensions like this: 242BB29A

I fear you'll have to analyse the file for yourself.

From offset 0x30 there is a table with entries refering to the stringtable starting at file offset 0x360.
Those entries might be: DWord string number (some are missing, such as 1, 5, and so on)
word string offset word const= 0x808A
examples: 
00000000 10 76 8A 80
02000000 23 76 8A 80
...

comparing the following table
strlen string
0x12 pausetitle_history
0x0F tab_pawnmessage
0x0D tab_pawnsused
0x10 tab_adventurelog
0x17 tab_pawnmessage_cinesco
0x15 tab_pawnsused_cinesco
...

and these offsets
0x7610
0x7623 0x13 (=0x7623-0x7610) = 0x12 + 1 (zero byte for string termination)
0x7633 0x10
0x7641 0x0E
0x7652 0x11
0x766A 0x18
0x7680 0x16
...

you'll come to the conclusion:
subtract (as a test only!) 0x72B0 to get the file offsets for the strings
0x360 (= 0x7610-0x72B0)
0x373: tab_pawnmessage
0x383: tab_pawnsused
0x391: tab_adventurelog

So for translation you might only have to adjust the offsets 0x7623, 0x7633 (and do the string translation, of course).
Didn't test it. (As I've said you don't need to do the subtraction of 0x72B0. It should just help to get the idea.)

If you try it with the last entry:
6F000000 95 7B 8A80
you'll get
0x8E5 tab_caption_cinesco4
but there are more strings to follow. So more research seems to be required.
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-01-30T16:44:08+00:00
- Post Title: HELP!!!How to open files with extensions like this: 242BB29A

Have a look at these sources:

import: [https://github.com/wmltogether/Phoenix- ... ort_gmd.py](https://github.com/wmltogether/Phoenix-Wright-5-iOS-Mod-Tools/blob/master/import_gmd.py)

export: [https://github.com/wmltogether/Phoenix- ... ort_gmd.py](https://github.com/wmltogether/Phoenix-Wright-5-iOS-Mod-Tools/blob/master/export_gmd.py)

alternatively, here's a script i just wrote:

```
//--- 010 Editor v5.0 Binary Template
//
// File:    pause_history_eng.2A2BB29A
// Author:  wrs
// Revision: 1
// Purpose:  GMD texts
//--------------------------------------

char magic[4]; // "GMD\0"
uint un;
uint unknown_1;
uint unknown_0a;
uint unknown_0b;

uint count_textkeys;
uint count_textval;

uint sizeof_textkeys;
uint sizeof_textval;

uint len;
char name[len + (4 - (len % 4))]; // pad to 4

struct data
{
  uint pid;
  int pstr; // may be -1
};

data lookup_tb[count_textkeys];

struct text {
  string val;
};

struct
{
  text keys[count_textkeys] <optimize=false>;
} TextKeys;

struct
{
  text values[count_textval] <optimize=false>;
} TextVal;

local int i;

for( i = 0; i < count_textkeys; ++i )
{
  Printf("%s == %s\n", TextKeys.keys[i].val, TextVal.values[lookup_tb[i].pid].val);
}

```


output:

note  shakotay2 is right - there are more values then keys!

> pausetitle_history == 
>
> tab_pawnmessage == Pawn Message Log
>
> tab_pawnsused == Pawns Used
>
> tab_adventurelog == Adventure Log
>
> tab_pawnmessage_cinesco == View recent conversations you've had with your pawns.
>
> Select pawn with <SIZE 23><ICON PAD_LS></SIZE>.
>
> tab_pawnsused_cinesco == View profiles of all the pawns you've ever
>
> enlisted. Select pawn with <SIZE 23><ICON PAD_LS></SIZE>.
>
> tab_adventurelog_cinesco == View records of your journey thus far.
>
> Select categories with <SIZE 23><ICON PAD_LS></SIZE>.
>
> list_currentpawns == Past Pawn Conversations
>
> list_oldpawns == Previously Used Pawns
>
> 
>
> .....
