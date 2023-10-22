## Post #1
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-07-30T07:40:10+00:00
- Post Title: DTA format

Hello, 
You can helpme, i need tool for DTA format Mafia game.
DTA Packer, you can trying make this.
Ican send file dta 250 Kb.
Thanks.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-07-30T07:40:52+00:00
- Post Title: DTA format

send file dta 250kb
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-07-30T17:54:16+00:00
- Post Title: DTA format

Got em, thanks for that document. That's quit a read! Hmm...
## Post #4
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-07-31T09:33:57+00:00
- Post Title: DTA format

> Reply from Mr.Mouse
>
> Got em, thanks for that document. That's quit a read! Hmm...
How you work on dta format?
You can make Packer?
## Post #5
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-03T05:50:37+00:00
- Post Title: DTA format

> Reply from Anonymous
>
> Mr.Mouse wrote:Got em, thanks for that document. That's quit a read! Hmm...
How you work on dta format?
You can make Packer?

Mr. Mouse HELLO.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-03T11:18:16+00:00
- Post Title: DTA format

Hello, yes, I'm trying to figure out this stuff. it will take some time.
## Post #7
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-03T17:33:52+00:00
- Post Title: DTA format

> Reply from Mr.Mouse
>
> Hello, yes, I'm trying to figure out this stuff. it will take some time.
OK, I shall wait. Thanks!
## Post #8
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-12T12:21:11+00:00
- Post Title: DTA format

Hello again! 
You already even approximately know, can make the Packer for DTA ?
## Post #9
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-13T14:10:53+00:00
- Post Title: DTA format

Hi there,

Making a packer is typically far more difficult than making an unpacker because for a packer you need to know what every byte of data in the DTA file means. Even if you don't know what 1 single byte means, you are stuffed.

Seeing as though Mr Mouse hasn't done any implementation for the DTA format, i think its probably safe to assume it is a very difficult format to understand, and thus it would be practically impossible to write a packer at this stage.

Keep checking back, over time we may have something that can help you.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #10
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-13T14:25:37+00:00
- Post Title: DTA format

> Reply from friendsofwatto
>
> Hi there,

Making a packer is typically far more difficult than making an unpacker because for a packer you need to know what every byte of data in the DTA file means. Even if you don't know what 1 single byte means, you are stuffed.

Seeing as though Mr Mouse hasn't done any implementation for the DTA format, i think its probably safe to assume it is a very difficult format to understand, and thus it would be practically impossible to write a packer at this stage.

Keep checking back, over time we may have something that can help you.

WATTO
watto@watto.org
http://www.watto.org
You don know, how compression method is using DTA files?
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-13T14:32:48+00:00
- Post Title: DTA format

To be honest, WATTO, he has send me a text file that would explain a lot of the format and its compression, if I remember correctly. Whether it is difficult or not, I'm ashamed to say I still have to look at it.    

Tell you what, I don't have that document here, but I'll mail post it here if I get home. Perhaps 'Guest' can even post it again, but in this thread (you can attach it to a reply).
## Post #12
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-13T14:58:55+00:00
- Post Title: DTA format

OK, thanks Mr Mouse, I can take a look at it. I should really stop answering these posts for you shouldn't I 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #13
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-13T16:21:22+00:00
- Post Title: DTA format

[quote="friendsofwatto"]OK, thanks Mr Mouse, I can take a look at it. I should really stop answering these posts for you shouldn't I 

WATTO
[watto@watto.org](mailto:watto@watto.org)
OK. You know compression method?
And Mr. Mouse you can make tool, i not undestend.
Thanks.
Accessing Mafias DTA files

by MassaSnygga



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
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-13T18:37:43+00:00
- Post Title: DTA format

As I said: quite a read!
## Post #15
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-13T18:54:10+00:00
- Post Title: DTA format

Hes LUCKY, most dll's like that, are exported by ordinal instead of by name, to prevent debugging, This is how diablo worked, and it was INSANE to debug, but i did it
## Post #16
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-13T19:15:05+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> As I said: quite a read!
Well you nevertheless try to make the Packer!
OK.
## Post #17
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-13T19:47:35+00:00
- Post Title: 

Listen Mr. Mouse, I so understand that you yet have not read up to the end the document about DTA files, so?
For all this time, you already should look on DTA a file, and at the document 
Also you can be defined to make the utility whether or not.
I do not want to hurry or demand from you that that.
I simply want to understand, know for certain, it is necessary to me to wait whether or not.
## Post #18
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-14T12:06:22+00:00
- Post Title: 

Well looking at the document you supplied, it wont be possible to make a packer, mostly because there are too many unknowns. Sure, we could just put random data in those fields, but because we don't know what it represents, it probably wouldn't work in the game.

Also, I don't really like supporting games that use different keys for each file, because those games don't let people create their own archives that are compatable with the game, unless the archives use the exact key and filename that was specified in the program executable - basically means that the game developers have prevented any modding - a real disappointment. Anyway, thats just my opinion 

So, in answer to your question, I doubt very much that anyone here would be able to create a packer that would work for the game, unless we knew for sure what each unknown field represented.

Sorry, good luck though to anyone else attempting this.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
