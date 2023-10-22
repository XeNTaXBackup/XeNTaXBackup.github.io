## Post #1
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-12-20T18:11:38+00:00
- Post Title: Myst IV -- patch.m4b how unpack and repack txt files?

Hi,
I want to localize this game,
but I couldn't open the file.can you help?
example
[http://www.mediafire.com/download/t553j ... ch.m4b.m4b](http://www.mediafire.com/download/t553jarv47akp6v/patch.m4b.m4b)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-12-20T23:48:02+00:00
- Post Title: Myst IV -- patch.m4b how unpack and repack txt files?

this patch file is referencing subtitles in .bin files - such as "subtitle_p_atr2_s03_p05.bin"

does the game include those? this m4b is just a patch delta format:

```
//--------------------------------------
//--- 010 Editor v5.0 Binary Template
//
// File:        patch.m4b parser (Myst IV)
// Author:      WRS (XeNTaX.com)
// Revision:    1
// Purpose:     Patch parser
//--------------------------------------

#include "prelen.bt";

// Forward decl.
struct RecNode;

struct File
{
  str String(plen32);
  uint length;
  uint offset;

  Printf("[PATCHING] %s %u bytes @ %u\n", String.val, length, offset);
};

struct RecNode
{
  str String(plen32);
  ubyte num;

  if( num > 0 )
  {
    RecNode children[num] <optimize=false>;

    uint unknown_0; Assert(unknown_0 == 0);
  }
  else
  {
    uint files; Assert(files > 0);
    File file_child[files] <optimize=false>;
  }
};

struct Hd
{
    // UBI_BG_SIG
    str Sig(plen32);
    
    uint unknown_0; Assert(unknown_0 == 1);
    uint unknown_1; Assert(unknown_1 == 0);

    ubyte num_child; Assert(num_child > 0 );

    if( num_child > 0 )
    {
      RecNode child[num_child] <optimize=false>;
    }

    uint Langs;

    struct Lang
    {
      str Lang1(plen32);
      uint z, x;
    
      Printf("%s\n", Lang1.val);
    };
    
    Lang langs_[Langs] <optimize=false>;
};

// Actual data isn't stored like this - the script just parses as an example
Hd a, b;


```
## Post #3
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-12-21T04:07:25+00:00
- Post Title: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from WRS
>
> this patch file is referencing subtitles in .bin files - such as "subtitle_p_atr2_s03_p05.bin"

does the game include those? this m4b is just a patch delta format:

This is delta format. But, how can I use the code?
I have not never written a program before

Here is Original file: [http://www.mediafire.com/download/yb86l ... /patch.m4b](http://www.mediafire.com/download/yb86lsfp4mew8le/patch.m4b)
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-12-21T15:02:25+00:00
- Post Title: Myst IV -- patch.m4b how unpack and repack txt files?

it's a template for 010 editor - [http://www.sweetscape.com/010editor/](http://www.sweetscape.com/010editor/)

that patch.m4b is the same as the one you posted above!!!!! post a sample of the .bin files
## Post #5
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-12-21T15:58:37+00:00
- Post Title: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from WRS
>
> it's a template for 010 editor - http://www.sweetscape.com/010editor/

that patch.m4b is the same as the one you posted above!!!!! post a sample of the .bin files

other game the file size is 300MB. also I threw that single file language file. And to use 010editor, unfortunately I don't know. Do you have the possibility to export in the form of more detailed or CMD code
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-12-21T16:02:41+00:00
- Post Title: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from Taner038
>
> WRS wrote:it's a template for 010 editor - http://www.sweetscape.com/010editor/

that patch.m4b is the same as the one you posted above!!!!! post a sample of the .bin files 

other game the file size is 300MB. also I threw that single file language file. And to use 010editor, unfortunately I don't know. Do you have the possibility to export in the form of more detailed or CMD code

the script just arranges the file contents:



it just contains patch information. if you want to unpack the language files you need to give a language file. the patch information says these are bin files. without them i can't do anything
## Post #7
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-12-21T16:21:49+00:00
- Post Title: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from WRS
>
> Taner038 wrote:WRS wrote:it's a template for 010 editor - http://www.sweetscape.com/010editor/

that patch.m4b is the same as the one you posted above!!!!! post a sample of the .bin files 

other game the file size is 300MB. also I threw that single file language file. And to use 010editor, unfortunately I don't know. Do you have the possibility to export in the form of more detailed or CMD code

the script just arranges the file contents:



it just contains patch information. if you want to unpack the language files you need to give a language file. the patch information says these are bin files. without them i can't do anything

Ok. I will send the shortest time. Thanx again. You're good man.
## Post #8
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-12-21T17:18:36+00:00
- Post Title: Myst IV -- patch.m4b how unpack and repack txt files?

I can get the language files of the game by using the rival tools.
letters with a hex editor I can transfer it on the screen and also the game looks.
The file I dropped this translation can be made. 
The problem is that letters have a limit. 

Rival tools here: [https://www.sendspace.com/file/fhdkxq](https://www.sendspace.com/file/fhdkxq)


these tools unpack the language files but can't repack.

I have to repack tools. 

@WRS
## Post #9
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-12-21T18:13:44+00:00
- Post Title: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from Taner038
>
> The problem is that letters have a limit.

how do you know this if you can't repack stuff?
## Post #10
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-12-21T21:19:24+00:00
- Post Title: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from WRS
>
> Taner038 wrote:The problem is that letters have a limit. 

how do you know this if you can't repack stuff?

I'm using hex editor.
## Post #11
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-12-21T22:15:55+00:00
- Post Title: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from Taner038
>
> I can get the language files of the game by using the rival tools.
letters with a hex editor I can transfer it on the screen and also the game looks.
The file I dropped this translation can be made. 
The problem is that letters have a limit. 

Rival tools here: https://www.sendspace.com/file/fhdkxq


these tools unpack the language files but can't repack.

I have to repack tools. 

@WRS

the java decompilers are horrible. uploate the resource somewhere and i'll take a look at the actual data. no point porting bytecode
## Post #12
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-12-21T22:21:42+00:00
- Post Title: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from WRS
>
> 
the java decompilers are horrible. uploate the resource somewhere and i'll take a look at the actual data. no point porting bytecode

if you could find a solution it would make me very happy. 
translation with a hex editor sucks :s :s
## Post #13
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-12-23T02:48:07+00:00
- Post Title: Myst IV -- patch.m4b how unpack and repack txt files?

Up.
## Post #14
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-12-24T08:00:35+00:00
- Post Title: Myst IV -- patch.m4b how unpack and repack txt files?

Here WRS the main file: [http://www.mediafire.com/download/7pc50 ... y/data.rar](http://www.mediafire.com/download/7pc50f3b9sb5dpy/data.rar)
## Post #15
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-12-25T11:29:50+00:00
- Post Title: Myst IV -- patch.m4b how unpack and repack txt files?

Up.
## Post #16
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-12-27T13:02:30+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

Up.
## Post #17
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-12-28T00:08:17+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

its the holidays!

have a function to descramble the bin filenames

```
{
  local int i;
  local string s = "";
  for(i=0; i <x.len; ++i)
  {
    switch( (ubyte)x.val[i] )
    {
// from "t_credits" and "t_frequency"
// subtitle_p_a0c_s81_p02
// subtitle_p_ach_s17_p01_flash
case 0x30: s+= "0"; break; // 0
case 0x32: s+= "1"; break; // 2
case 0x31: s+= "2"; break; // 1
case 0x33: s+= "3"; break; // 3

case 0x3b: s+= "7"; break; // b
case 0x34: s+= "8"; break; // 4
// ------------------------------
case 0x92: s+= "a"; break; // 2
case 0x91: s+= "b"; break; // 1
case 0x93: s+= "c"; break; // 3
case 0x98: s+= "d"; break; // 8
case 0x9a: s+= "e"; break; // a
case 0x99: s+= "f"; break; // 9
case 0x9b: s+= "g"; break; // b
case 0x94: s+= "h"; break; // 4
case 0x96: s+= "i"; break; // 6
case 0x95: s+= "j"; break; // 5
//case 0x9: s+= "k? "; break; // guess ??
case 0x9c: s+= "l"; break; // c
case 0x9e: s+= "m"; break; // e
case 0x9d: s+= "n"; break; // d
case 0x9f: s+= "o"; break; // f
// ------------------------------
case 0xb0: s+= "p"; break; // 0
case 0xb2: s+= "q"; break; // 2
case 0xb1: s+= "r"; break; // 1
case 0xb3: s+= "s"; break; // 3
case 0xb8: s+= "t"; break; // 8
case 0xba: s+= "u"; break; // a
case 0xb9: s+= "v"; break; // 9
case 0xbb: s+= "w? "; break; // guess b
case 0xb4: s+= "x? "; break; // guess 4
case 0xb6: s+= "y"; break; // 6
case 0xb5: s+= "z? "; break; // guess 5
// ------------------------------
case 0xaf: s += "_"; break; // f0
default : 
//Assert(false);
 s += "?? ";
    }
  }

  Printf("%s\n", s);
}

```


(it just swaps around bit pairs)
## Post #18
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-12-28T07:11:34+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

Thanks, but I do not understand. Exactly what I need to do this code and what does it do?

Edit: I do not understand programming. I'm a translator and I do not understand these issues.

here game folder, no other data file or bin file.
## Post #19
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-12-28T09:21:52+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from Taner038
>
> Thanks, but I do not understand. Exactly what I need to do this code and what does it do?

Edit: I do not understand programming. I'm a translator and I do not understand these issues.

it is just an update. im working on something for myst i'll post in a few days.
## Post #20
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-12-28T14:03:20+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from WRS
>
> Taner038 wrote:Thanks, but I do not understand. Exactly what I need to do this code and what does it do?

Edit: I do not understand programming. I'm a translator and I do not understand these issues.


it is just an update. im working on something for myst i'll post in a few days.

My grateful thanks.
## Post #21
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-01-01T18:10:09+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

Any progress WRS?
## Post #22
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-01-02T17:48:51+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

edit work in progress

[https://github.com/x1nixmzeng/mystiv-loc-tools](https://github.com/x1nixmzeng/mystiv-loc-tools)
## Post #23
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-01-07T08:19:24+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

Any progress WRS?
## Post #24
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-01-07T23:18:13+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from Taner038
>
> Any progress WRS?

yeah that sourcecode can extract the m4b files and dump the english strings to xml. unfortunately i dont have any time to work on repacking it at the moment   

i'll attach the tools as they are - the xml convert just prints the console - so pipe it like this:

```
myst_loc file.bin > output.xml
```

[myst_tools.zip](https://xentaxbackup.github.io/file/10279_myst_tools.zip)
## Post #25
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-01-08T00:11:27+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from WRS
>
> Taner038 wrote:Any progress WRS?  

yeah that sourcecode can extract the m4b files and dump the english strings to xml. unfortunately i dont have any time to work on repacking it at the moment   

i'll attach the tools as they are - the xml convert just prints the console - so pipe it like this:
Code: Select allmyst_loc file.bin > output.xml

Thank you very much, but I'm confused,

There is no file .bin file,

How do I unpack the file patch.m4b

I use the following cmd code gives an error:

CMD CODE:

```
pause

```



EDIT: I found .bin files but still failed unpack says
## Post #26
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2016-01-09T04:00:03+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from Taner038
>
> EDIT: I found .bin files but still failed unpack says
Try data.m4b_Unpack.bat

```
md data\w1\z04\n111
md data\w1\z04\n121
md data\w1\z04\n122
md data\w1\z04\n131
md data\w1\z05\n011
md data\w1\z05\n020
md data\w1\z05\n032
md data\w1\z05\n051
md data\w1\z05\n052
md data\w1\z06\n011
md data\w1\z07\n021
md data\w1\z07\n022
md data\w1\z07\n032
md data\w1\z07\n033
md data\w1\z07\n041
md data\w1\z09\n021
md data\w1\z09\n041
md data\w1\z09\n061
md data\w1\z09\n062
md data\w2\z01\n061
md data\w2\z01\n132
md data\w2\z01\n141
md data\w2\z01\n171
md data\w2\z01\n181
md data\w2\z01\n191
md data\w2\z02\n015
md data\w2\z03\n073
md data\w2\z04\n061
md data\w2\z05\n081
md data\w2\z05\n132
md data\w2\z06\n011
md data\w2\z06\n093
md data\w2\z06\n094
md data\w2\z06\n153
md data\w2\z06\n154
md data\w2\z06\n171
md data\w2\z07\n022
md data\w2\z07\n051
md data\w2\z07\n061
md data\w2\z12\n031
md data\w2\z12\n151
md data\w2\z12\n192
md data\w3\z01\n021
md data\w3\z01\n121
md data\w3\z01\n122
md data\w3\z01\n133
md data\w3\z02\n051
md data\w3\z02\n071
md data\w3\z02\n102
md data\w3\z02\n103
md data\w3\z02\n104
md data\w3\z02\n151
md data\w3\z02\n202
md data\w3\z02\n211
md data\w3\z02\n231
md data\w3\z03\n010
md data\w3\z03\n011
md data\w3\z03\n050
md data\w3\z03\n051
md data\w3\z03\n052
md data\w3\z03\n053
md data\w3\z03\n061
md data\w3\z03\n062
md data\w3\z03\n072
md data\w3\z04\n131
md data\w3\z04\n151
md data\w3\z04\n161
md data\w3\z04\n200
md data\w3\z05\n020
md data\w3\z05\n021
md data\w3\z05\n081
md data\w3\z05\n111
md data\w3\z06\n051
md data\w3\z06\n052
md data\w4\z01\n011
md data\w4\z02\n181
md data\w4\z02\n241
md data\w4\z03\n010
md data\w4\z03\n021
md data\w4\z03\n050
md data\w4\z03\n051
md data\w4\z03\n061
md data\w4\z03\n071
md data\w4\z03\n081
md data\w4\z03\n090
md data\w4\z03\n091
md data\w4\z03\n092
md data\w4\z04\n020
md data\w4\z04\n021
md data\w4\z04\n031
md data\w4\z04\n050
md data\w4\z04\n051
md data\w4\z04\n090
md data\w4\z04\n091
md data\w4\z04\n092
md data\w4\z04\n161
md data\w4\z04\n200
md data\w4\z04\n201
md data\w4\z04\n230
md data\w4\z04\n240
md data\w4\z05\n031
md data\w4\z05\n050
md data\w4\z05\n051
md data\w4\z05\n130
md data\w4\z05\n131
md data\w4\z06\n061
md data\w4\z06\n131
md data\w4\z06\n161
md data\w4\z06\n200
md data\w4\z06\n210
md data\w4\z06\n230
md data\w4\z06\n231
md data\w4\z06\n232
md data\w4\z06\n260
md data\w4\z06\n310
md data\w4\z06\n320
md data\w5\z01\n010
md data\w5\z01\n241
md data\w5\z02\n030
md data\w5\z02\n031
md data\w5\z04\n040
md data\w5\z04\n050
md data\w5\z04\n090
md data\w5\z04\n110
md data\w5\z04\n130
md data\w5\z09\n041
md data\w5\z09\n061
md data\w6\z01\n021
md data\w6\z06\n011
md data\w6\z06\n021
md data\w6\z06\n031
md data\w6\z06\n041
md data\w6\z06\n051
md data\w6\z06\n061
md data\w6\z06\n071
md data\w6\z06\n081
md data\w6\z06\n082
md data\w6\z06\n083
md data\w6\z06\n084
md data\w6\z06\n091
md data\w6\z06\n111
myst_m4b.exe e data.m4b data
```
## Post #27
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-01-09T15:13:32+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

Thkx makcar

but I stuck in this time when you unpack the .bin file. Tools turns giving error.

example (.bin file):
[http://www.mediafire.com/download/fe2bf ... 79_v02.rar](http://www.mediafire.com/download/fe2bfhyjax1xxvt/subtitle_p_cat_s79_v02.rar)
## Post #28
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2016-01-09T17:24:30+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

Only this files: data\w6\z06\n011\*.bin

.bin_Unpack.bat

```
myst_loc.exe t_credits.bin t_credits.xml
myst_loc.exe t_cursor_menu.bin t_cursor_menu.xml
myst_loc.exe t_game_menu.bin t_game_menu.xml
myst_loc.exe t_graphics_menu.bin t_graphics_menu.xml
myst_loc.exe t_helpmap.bin t_helpmap.xml
myst_loc.exe t_journal.bin t_journal.xml
myst_loc.exe t_load_menu.bin t_load_menu.xml
myst_loc.exe t_main_menu.bin t_main_menu.xml
myst_loc.exe t_save_menu.bin t_save_menu.xml
```
## Post #29
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-01-09T19:02:40+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

sorry there are a few issues with the tools -

makcar is right - it does not create directories when it extracts
also there are different bin types which aren't handled.
## Post #30
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-01-10T10:18:19+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from WRS
>
> sorry there are a few issues with the tools -

makcar is right - it does not create directories when it extracts
also there are different bin types which aren't handled.

I look forward to updating and repack
## Post #31
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-01-13T04:50:07+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

Up.
## Post #32
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-01-14T13:16:57+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

Up.
## Post #33
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-01-15T20:24:15+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

WRS; where are you, mate?
Up.
## Post #34
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-01-16T23:41:31+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

attached latest myst_loc which converts bin -> xml and back again

repacking m4b soon
[myst_loc.7z](https://xentaxbackup.github.io/file/10324_myst_loc.7z)
## Post #35
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-01-17T19:43:12+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from WRS
>
> attached latest myst_loc which converts bin -> xml and back again

repacking m4b soon

Edit: still is not doing all .bin files XML

Example:

```

```
## Post #36
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-01-18T23:54:11+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

should now support subtitles
[myst_loc.7z](https://xentaxbackup.github.io/file/10335_myst_loc.7z)
## Post #37
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-01-19T07:48:41+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from WRS
>
> should now support subtitles

now work. 
I'm starting localization.
I look forward to repack tools. 
Thank you very much.
Turkish players owe you a lot
## Post #38
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-01-23T01:51:49+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

I'm almost finished the translation.
I waited repack WRS
Thanks again.
## Post #39
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-01-23T14:56:00+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

beware - there is a bug with m4b extraction

common/t_error.bin should have been common/text/t_error.bin

you may have to move some of your edited files

i'll give a new exe soon
## Post #40
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-01-23T15:24:27+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from WRS
>
> beware - there is a bug with m4b extraction

common/t_error.bin should have been common/text/t_error.bin

you may have to move some of your edited files

i'll give a new exe soon

Its not problem. So there repack development?
## Post #41
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-01-24T19:01:36+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from Taner038
>
> WRS wrote:beware - there is a bug with m4b extraction

common/t_error.bin should have been common/text/t_error.bin

you may have to move some of your edited files

i'll give a new exe soon

Its not problem. So there repack development?

yup. here you go  
[myst_iv_tools.7z](https://xentaxbackup.github.io/file/10361_myst_iv_tools.7z)
## Post #42
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-01-24T19:58:16+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

Is this repack support?  WRS
## Post #43
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-01-24T21:26:12+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from Taner038
>
> Is this repack support?  WRS

yes - please give it a try!

it isn't an identical repack. the list of files returned by windows is not sorted, and this tool doesn't sort them either. but it should work for translations.

full source on [https://github.com/x1nixmzeng/mystiv-loc-tools](https://github.com/x1nixmzeng/mystiv-loc-tools)
## Post #44
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-01-24T21:57:44+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from WRS
>
> Taner038 wrote:Is this repack support?  WRS 

yes - please give it a try!

it isn't an identical repack. the list of files returned by windows is not sorted, and this tool doesn't sort them either. but it should work for translations.

full source on https://github.com/x1nixmzeng/mystiv-loc-tools

I worked the night shift but I would look in the morning.  
Thanks for the work
you're very good man.
## Post #45
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2016-02-06T14:00:35+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from WRS
>
> Taner038 wrote:Is this repack support?  WRS 

yes - please give it a try!

it isn't an identical repack. the list of files returned by windows is not sorted, and this tool doesn't sort them either. but it should work for translations.

full source on https://github.com/x1nixmzeng/mystiv-loc-tools

hi,WRS,i can't use this tool to extract common.m4b which extracted from data.m4b.
common.m4b can be download from here,can you take a look? Thanks.  
[http://www.mediafire.com/download/k23gc ... common.m4b](http://www.mediafire.com/download/k23gcdocbx5e8r2/common.m4b)
## Post #46
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-02-06T14:27:07+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from stevenx
>
> hi,WRS,i can't use this tool to extract common.m4b whick extracted from data.m4b.

hi stevenx - thanks for reporting this. i'm working on a fix!

edit: see attached
[myst_iv_tools.7z](https://xentaxbackup.github.io/file/10434_myst_iv_tools.7z)
## Post #47
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2016-02-06T14:50:33+00:00
- Post Title: Re: Myst IV -- patch.m4b how unpack and repack txt files?

> Reply from WRS
>
> stevenx wrote:hi,WRS,i can't use this tool to extract common.m4b whick extracted from data.m4b.

hi stevenx - thanks for reporting this. i'm working on a fix!

edit: see attached

Thanks for your fast response, it worked!
