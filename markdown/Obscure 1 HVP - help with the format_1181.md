## Post #1
- Username: pulposo
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-04-16T12:59:12+00:00
- Post Title: Obscure 1 HVP - help with the format

Hi to all!! 

your program it's really good!!
I'm looking for the nexts plugins packer/unpacker:

For "Obscure" game.

I you want i can send to you a sample of the file.
Thanks
## Post #2
- Username: pulposo
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-04-16T14:22:33+00:00
- Post Title: Obscure 1 HVP - help with the format

The smallest file i found it's 26mb's and i can't pack it (likz 7-zip , rar, uharc or zip), i can send to you, you want it anyway?

Thanks, next time i try to register.
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-16T14:59:11+00:00
- Post Title: Obscure 1 HVP - help with the format

Well, if you have a hex editor, you can cut the first and last 500kb of the file and send those pieces to us, or try to upload the file to a web server somewhere. 26MB is a little too big to send via my email 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-04-17T09:59:18+00:00
- Post Title: Obscure 1 HVP - help with the format

Anyway i think ppl can download the demo (346mb's) for analyze the data files. I know it'a huge file size for a demo..but i'm trying to found a smallest  size.
But by now:
javascript:downloadNow('[http://www.obscure-game.com/demo/obscur ... 2.html','0](http://www.obscure-game.com/demo/obscure_demo.zip%27,%27http://dw.com.com/redir?pid=10312262&merid=57971&mfgid=57971&ltype=dl_dlnow&lop=btn&edId=3&siteId=4&oId=3640-7504_4-10312262&ontId=7504_4&destUrl=http://www.download.com%2F3001-7504_4-10312262.html%27,%270)')
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2005-04-17T10:02:45+00:00
- Post Title: Obscure 1 HVP - help with the format

I found a smallest file size, a repack in a russian web:
[http://vip.ag.ru/download/demos/12649/o ... repack.exe](http://vip.ag.ru/download/demos/12649/obscure_demo_xtreme_repack.exe)
It's a 126mb's
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-17T12:11:47+00:00
- Post Title: Obscure 1 HVP - help with the format

Hi again,

I got your email - I will take a look at the file. I don't think I will be downloading the demo though - its just too big for a 56k dialup modem 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #7
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-04-19T18:20:11+00:00
- Post Title: Obscure 1 HVP - help with the format

hello

this is one pack from obscure game
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2005-04-19T19:31:31+00:00
- Post Title: Obscure 1 HVP - help with the format

Okay, thanks, but i'm looking for the packer and unpacker, to make my own hpv file, 'coz i want to translate the game (voices) to other language.
## Post #9
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-20T05:54:42+00:00
- Post Title: Obscure 1 HVP - help with the format

I have taken a look at it - it is a bit of a tricky structure but I have almost got it. We *should* be able to add support for this game soon.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #10
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-21T12:21:25+00:00
- Post Title: Obscure 1 HVP - help with the format

OK, the format is something like this...

```
| Obscure *.hvp |
+---------------+

// This whole archive looks to be encrypted/compressed or something, as 
// there is a lack of null bytes.

11 - Header (HV PackFile)
2 - null
2 - Unknown (3)
4 - Unknown (1)
2 - Unknown (1)
1 - null
4 - Unknown
4 - Unknown
10 - Unknown

// for each directory?
  3 - null
  1 - Unknown
  4 - Entry Type? (0=dir, 1=file)
  if (entryType == dir){
    4 - null
    4 - null
    4 - Number Of Files/SubDirectories In This Directory
    }
  else if (entryType == file){
    2 - Unknown (1)
    4 - Unknown
    4 - Unknown
    4 - Unknown
    2 - Unknown
    4 - Unknown
    1 - Filename Length
    X - Filename
    }
```


However I am finding it hard to work out the offsets and lengths of each file, more-so because the archive appears to be encrypted or compressed or something. I will continue to look at it some more, but it may not be as easy to implement as I originally thought 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #11
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-04-21T12:50:12+00:00
- Post Title: Obscure 1 HVP - help with the format

hello

thank you mr watto

Iam attach new file from obscure game

good luck
## Post #12
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-22T04:55:28+00:00
- Post Title: Obscure 1 HVP - help with the format

Firstly, the files *.001 have the same format as the other *.hvp files

Secondly, I was right, the files are compressed, using ZLib.

Thord, I was reading the numbers the wrong way around  - when I read the the correct way they all make a lot more sence...

```
| Obscure *.hvp *.001 |
+---------------------+

// BIG ENDIAN ORDERING
// Uses ZLib compression

11 - Header (HV PackFile)
1 - null
4 - Unknown
4 - Unknown (8)
4 - Number Of Files and Directories
4 - Number Of Files only
4 - Directory Length (not including all these archive header fields)
8 - Unknown

// for each directory?
  4 - Length Of Entry (including this field)
  1 - Entry Type Indicator 1 (0=dir, 1=file)
  4 - Entry Type Indicator 2 (0=dir, 1=file)
  if (entryType == dir){
    4 - Number Of Files/SubDirectories In This Directory
    1 - Directory Name Length
    X - Directory Name
    }
  else if (entryType == file){
    4 - Compressed Size
    4 - Decompressed Size
    4 - Unknown (Hash or something?)
    4 - File Offset
    4 - Filename Length
    X - Filename
    }
    
X - File Data
```


Therefore, the structure is nice and easy to read, so we should be able to write a script for this game. Sorry it has taken so long, I was sure I was reading the numbers the rght way around. Now all I have to do is work out how to read big-endian numbers in MexCom and get a script to you.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-22T06:18:37+00:00
- Post Title: Obscure 1 HVP - help with the format

Use 
```
ReverseLong <var>
```
## Post #14
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-22T09:39:03+00:00
- Post Title: Obscure 1 HVP - help with the format

OK, I will get a script done whenever I get the time.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #15
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-04-23T10:22:00+00:00
- Post Title: Obscure 1 HVP - help with the format

Hi Watto you remember me!?
I have just make an extractor for this game a lot of day ago.

```
| Obscure *.hvp *.001 |
+---------------------+

// BIG ENDIAN ORDERING
// Uses ZLib compression

11 - Header (HV PackFile)
4 - Archive Version? (is not null)
1 - 1 (I think is a flag to indicate that using compression)
4 - Number Of Roots dir
4 - Number Of Files and Directories
4 - Number Of Files only
4 - Directory Length (not including all these archive header fields)
8 - Unknown (I think is a type of checksum)

// for each roots directory?
  4 - Length Of Entry (including this field)
  1 - Entry Type Indicator 1 (0=dir, 1=file)
  4 - Compression flag (o=not compressed, 1=compressed)
  if (entryType == dir){
    4 - Number Of Files/SubDirectories In This Directory
    1 - Directory Name Length
    X - Directory Name
    }
  else if (entryType == file){
    4 - Compressed Size
    4 - Decompressed Size
    4 - Unknown (Hash or something? I think is a type of checksum)
    4 - File Offset
    4 - Filename Length
    X - Filename
    }
   
X - File Data

```


bye
## Post #16
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-23T14:16:41+00:00
- Post Title: 

Hey mate,

Excellent work on the extractor for that game - I would be keen to see it.


WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #17
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2005-04-23T22:10:01+00:00
- Post Title: 

sure

C++ language, it use zlib1.dll (hxxp://[www.zlib.org/](http://www.zlib.org/))

bye friend!  
[unhvp.zip](https://xentaxbackup.github.io/file/186_unhvp.zip)
## Post #18
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2005-04-24T08:40:45+00:00
- Post Title: 

Thanks now i have the unpacker...

how i can compile the unpacker i use M$ Visual C++ 6 and give the next error:

c:\!\a3\unhvp.cpp(5) : fatal error C1083: Cannot open include file: 'zlib.h': No such file or directory

But the zlib.h it's in the directory

Any version compiled ? , thanks.
## Post #19
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2005-04-24T10:27:28+00:00
- Post Title: 

@pulposo
you must download precompiled dll from hxxp://[www.zlib.net/zlib122-dll.zip](http://www.zlib.net/zlib122-dll.zip)
extract zlib.h and zconf.h in include folder Visual C++ and zdll.exp, zdll.lib in lib folder then add them in your project.
bye
## Post #20
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2005-04-24T10:38:15+00:00
- Post Title: 

Sorry, but dont' work. 

```
unhvp.cpp
C:\obscure\unhvp.cpp(24) : error C2065: 'memcmp' : undeclared identifier
C:\obscure\unhvp.cpp(30) : error C2065: 'strchr' : undeclared identifier
C:\obscure\unhvp.cpp(30) : error C2440: '=' : cannot convert from 'int' to 'char *'
        Conversion from integral type to pointer type requires reinterpret_cast, C-style cast or function-style cast
C:\obscure\unhvp.cpp(119) : error C2440: '=' : cannot convert from 'char *' to 'unsigned char *'
        Types pointed to are unrelated; conversion requires reinterpret_cast, C-style cast or function-style cast
C:\obscure\unhvp.cpp(121) : error C2440: '=' : cannot convert from 'char *' to 'unsigned char *'
        Types pointed to are unrelated; conversion requires reinterpret_cast, C-style cast or function-style cast
Error executing cl.exe.

unhvp.exe - 5 error(s), 0 warning(s)

```


I copied the files of "include" to "include" of M$ Visual, and the "lib" to "lib" of M$ Visual, then i tried to compile it but.
Any compiled version?

plz.
## Post #21
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2005-04-24T13:02:42+00:00
- Post Title: 

This is compiled version, included dll files.

```

```
## Post #22
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2005-04-24T20:42:46+00:00
- Post Title: 

Thanks it works really great!!!
## Post #23
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-25T11:53:22+00:00
- Post Title: 

I have done the Game Extractor plugin for the format - you can get it in the latest update (for those of you with the full version).

If you still want a script for this format, let me know and I will give it a try.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #24
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-12-16T10:36:54+00:00
- Post Title: 

hello

please look new hvp obscure game 

ps2 format, dont open with plugins

thanks
[VOX_EN.zip](https://xentaxbackup.github.io/file/492_VOX_EN.zip)
## Post #25
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-12-21T20:17:56+00:00
- Post Title: 

hello mr watto 

thank you for plugins

iam sent you new file from ps2 version game

don't open with new plugin and show error message "no plugins.."

thank you
[strm.zip](https://xentaxbackup.github.io/file/499_strm.zip)
## Post #26
- Username: DuderDuder
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 10, 2010 10:12 pm
- Post datetime: 2014-01-12T22:56:18+00:00
- Post Title: 

> Reply from baccello
>
> This is compiled version, included dll files.
Code: Select allhttp://www.baccello.altervista.org/tmp/unhvp_compiled.zip
Sorry to bump this old topic, but would anyone still happen to have this?
I'm trying to get the oggs out of the strmpack_pc.hvp and while watto's game extractor sees the files, they come out as 1 byte files when I try to extract them. datapack.hvp extracts fine though, so I don't know what's up with the strmpack. Maybe I'm doing something wrong.
## Post #27
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2014-01-13T04:07:00+00:00
- Post Title: 

> Reply from DuderDuder
>
> baccello wrote:This is compiled version, included dll files.
Code: Select allhttp://www.baccello.altervista.org/tmp/unhvp_compiled.zip

Sorry to bump this old topic, but would anyone still happen to have this?

Theres a compiled exe in this download
[UnHVP v1.0 - HV PackFile Resource](http://ctpax-cheater.narod.ru/personal/unhvp.zip)

Source page
[http://ctpax-cheater.narod.ru/personal.htm](http://ctpax-cheater.narod.ru/personal.htm)
## Post #28
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-03-04T12:15:38+00:00
- Post Title: 

> Reply from AceWell
>
> Theres a compiled exe in this download
UnHVP v1.0 - HV PackFile Resource

Source page
http://ctpax-cheater.narod.ru/personal.htm
Can somebody please update this program with the PC version? The extraction is errornous (0kb-files).
Here's the header of the archive.
[strmpack_pc_head.zip](https://xentaxbackup.github.io/file/7067_strmpack_pc_head.zip)
## Post #29
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-19T15:32:15+00:00
- Post Title: 

Obscure 1 file format --> [http://wiki.xentax.com/index.php/Obscure_HVP](http://wiki.xentax.com/index.php/Obscure_HVP)
quickbms script for HVP archives --> [https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/ObsCure/Obscure_HVP_script.bms)


My research on HVP archives from Obscure 2 --> [viewtopic.php?p=188831#p188831](https://forum.xentax.com/viewtopic.php?p=188831#p188831)
Links to extractor and file format are shared there. I hope that it will be helpful to someone.
