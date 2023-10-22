## Post #1
- Username: Knuckels
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 09, 2005 10:34 pm
- Post datetime: 2005-04-26T00:06:03+00:00
- Post Title: Full Spectrum Warrior

hey guys. what about Full Spectrum Warrior ?
Anybody know a tool to extract the game files ?
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-26T02:17:49+00:00
- Post Title: Full Spectrum Warrior

Sure, we will take a look at it. Could you give us a small archive from the game to look at?

Thanks.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-04-28T12:30:07+00:00
- Post Title: Full Spectrum Warrior

hey there.

There are 2 different  Archives in the game.

One Folder called Audio that contains .xsb files.
The smallest file there is 1,84 kb big.

And the second Folder is called Chapters and contains .PAK files.
I think there must be Textures and stuff. The smallest file here is 25.8 Mb.

So i can upload a .xsb sample file but 25.8 mb is much too big i think.
Is there a way to split some files so you can work with just a part of it ?

greets Knuckels
## Post #4
- Username: Knuckels
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 09, 2005 10:34 pm
- Post datetime: 2005-04-28T12:32:51+00:00
- Post Title: Full Spectrum Warrior

Sorry forgott to log in 
[mapZoom.rar](https://xentaxbackup.github.io/file/199_mapZoom.rar)
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-28T13:17:09+00:00
- Post Title: Full Spectrum Warrior

> Reply from Anonymous
>
> hey there.

There are 2 different  Archives in the game.

One Folder called Audio that contains .xsb files.
The smallest file there is 1,84 kb big.

And the second Folder is called Chapters and contains .PAK files.
I think there must be Textures and stuff. The smallest file here is 25.8 Mb.

So i can upload a .xsb sample file but 25.8 mb is much too big i think.
Is there a way to split some files so you can work with just a part of it ?

greets Knuckels

Yes. [http://www.xentax.com/downloads/tools/filecutter.zip](http://www.xentax.com/downloads/tools/filecutter.zip)

This is a tool we created especially for this purpose. 

It will cut the front end and back end of a file and zip it so you can email or attach it here.  

Good luck!
## Post #6
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-05-20T11:05:03+00:00
- Post Title: Full Spectrum Warrior

Accessing Mafia DTA files

1. Introduction

As I often receive email from people that ask for information about the DTA files, because they want to code another DTA tool (like the often requested DTA-packer), I decided to write this document and provide anyone with all the information I gathered about DTA files.

This document completely describes the methods the MafiaDataXtractor uses to extract the content from the DTA files.

Please note that the information provided here is based on my personal inspection of the disassembled Mafia code, lengthy debugging sessions, logged function calls and pure guesses. It is in no way official and not confirmed to be correct, it just works for me. Some parts may be incorrect or just wrong. Therefore you should read this document with an open mind, and donâ€™t take everything for granted that is written here (btw: that applies to all written things). If you find anything that is wrong, please let me know.

I expect that you know C and a little bit of x86-Assembler otherwise you wont understand all of this. Please donâ€™t bug me with any questions regarding C and ASM.

But now, letâ€™s get to the fun partâ€¦

2. The encryption keys

As you may have guessed on inspecting DTA files with your hex editor, the files are encrypted. In fact some of them are also compressed, but I havenâ€™t dealt with the compression methods at all. To read from them you have to know two 32-bit keys which are different for (almost) every DTA file. Luckily I could find them quite easily while inspecting the disassembled GAME.EXE as they are stored there without any (serious) protection. These keys seem to be identical for every international version, as they all seem to use the same GAME.EXE, except the German version, but the keys of that version are identical nonetheless.

I provide the keys here for your reference:

Filename
Content 
Key 1
Key 2

A0.dta
Sounds
0xD8D0A975
0x467ACDE0

A1.dta
Missions
0x3D98766C
0xDE7009CD

A2.dta
Models
0x82A1C97B
0x2D5085D4

A3.dta
Animations I
0x43876FEA
0x900CDBA8

A4.dta
Animations II
0x43876FEA
0x900CDBA8

A5.dta
Difference Data
0xDEAC5342
0x760CE652

A6.dta
Textures
0x64CD8D0A
0x4BC97B2D

A8.dta
Patch 1.1
0xD8DD8FAC
0x5324ACE5

A7.dta
Records
0xD6FEA900
0xCDB76CE6

A9.dta
System Data
0x6FEE6324
0xACDA4783

AA.dta
Tables
0x5342760C
0xEDEAC652

AB.dta
Music
0xD8D0A975
0x467ACDE0

AC.dta
Animations III
0x43876FEA
0x900CDBA8

Please note that A8.dta was just recently introduced with the 1.1 Patch and is not present in the 1.0 Version of the game.

3. Using the rw_data.dll

The easiest approach to the extraction problem is to use Mafias own DLL. This file is â€œrw_data.dllâ€
[isdata.rar](https://xentaxbackup.github.io/file/240_isdata.rar)
