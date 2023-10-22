## Post #1
- Username: Fatal
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Nov 17, 2009 5:10 am
- Post datetime: 2009-11-16T22:02:11+00:00
- Post Title: Def Jam Fight FOr New York .big

Hey there,

I am working on Def Jam Fight For New York to edit some files...
No i have been looking for 3 days for a .VIV and .BIG unpacker.
Dragon Unpacker can unpack VIV but at BIG it crashes... I thought i was so close  I feel like i am failing.
Then I foung Game Extractor which can also unpack VIV but fails at BIG... 
Last one was XENTAX..... I Opened VIV and i saw it did support Def Jam and I smiled, when I tried to open 1 BIG file i got 2 errors ( Look at the attachment).
I was like : Why does it have to go wrong... I really want to get this somewhere, Also the program says you can modify .BIG files from Def Jam FFNY.

Im doing this because im tired of the same music in the game... And I wanna modify some cloth and some stuffs.. i did it with an naruto game and it went raelly good but it did not contain .big files or .o files... so yeh

Please can anyone help me?? He could also join me.. if he wants to

Thank you in advance
[errors.jpg](https://xentaxbackup.github.io/file/2534_errors.jpg)
## Post #2
- Username: Fatal
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-16T22:32:32+00:00
- Post Title: Def Jam Fight FOr New York .big

Ok, well can you upload an example .BIG file somewhere? See our list.
## Post #3
- Username: Fatal
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Nov 17, 2009 5:10 am
- Post datetime: 2009-11-16T22:49:13+00:00
- Post Title: Def Jam Fight FOr New York .big

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2009-11-17T16:27:06+00:00
- Post Title: Def Jam Fight FOr New York .big

BigGui works well with this file.
## Post #5
- Username: Fatal
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Nov 17, 2009 5:10 am
- Post datetime: 2009-11-17T16:47:29+00:00
- Post Title: Def Jam Fight FOr New York .big

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: grzesiek
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-17T21:35:28+00:00
- Post Title: Def Jam Fight FOr New York .big

The ssh contains 8-bit images of 512 x 92 (some) followed each by a palette (0x400 in size, BMP style).
## Post #7
- Username: Fatal
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Nov 17, 2009 5:10 am
- Post datetime: 2009-11-17T22:11:49+00:00
- Post Title: Def Jam Fight FOr New York .big

Woow...

And how can I open them?

I mean how did you get there...

I hope you can tell me


Thnx in advance
## Post #8
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2009-11-19T07:08:39+00:00
- Post Title: Def Jam Fight FOr New York .big

Mr. Mouse:

Anymore info about ssh files? I tried extract them for long time. On images is something visible but its wrong palette. Can you tell me where is palette? Sorry for my english.
## Post #9
- Username: Fatal
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Nov 17, 2009 5:10 am
- Post datetime: 2009-11-19T17:55:54+00:00
- Post Title: Def Jam Fight FOr New York .big

Well yeh i need to know to so i can continue my project 

Hopefully i can succeed
## Post #10
- Username: grzesiek
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-19T19:38:55+00:00
- Post Title: Def Jam Fight FOr New York .big

Look the format of the files is as follows:

```

[4]		Magic word "SHPS"
uint32		Archive size (total size of .ssh file)
uint32		Number of resources
[4]		Filename (first part)

// Resource entry (repeated 'number of resources' times)

[4]		Filename (second part)
utin32		Offset of resource data

// Resource data (each resource actually begins with 'Buy ERTS' followed by 16 zero bytes, but the offset pointers above skip this part)

[1]		Unknown, always 2
uint24		Size of the graphics bitmap part (24-bit value!) INCLUDING the 16-byte header
uint16		Width
uint16		Height
[n]		BITMAP (8-bit bitmap, of 256 colours)

[1]		Unknown, always 0x21
uint32		Size of colour table INCLUDING the 16-byte header
[11]		Unknown, always the same, possibly one value is also the number of colours (256)
[n]		Palette (RGBA format, where A is often 0x80) 
[16]		Another row of values 
[240]		"EAGL240 metal bin attachment for runtime texture management" followed by zero bytes
[32]		tail values

```
## Post #11
- Username: Fatal
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-19T20:42:09+00:00
- Post Title: Def Jam Fight FOr New York .big

```
Get AS Long 0 ;
Get FN Long 0 ;
GetDString FNP 4 0 ;
Set EXT1 String ".bitmap" ;
Set EXT2 String ".colours" ;
For T = 1 To FN ;
GetDString LNP 4 0 ;
Get OFF Long 0 ;
SavePos N 0 ;
GoTo OFF 0 ;
Get ID Byte 0 ;
Get BMS Byte 0 ;
Get B Byte 0 ;
Math B *= 256 ;
Math BMS += B ;
Get B Byte 0 ;
Math B *= 65536 ;
Math BMS += B ;
Get W Int 0 ;
Get H Int 0 ;
Get U1 Long 0 ;
Get U1 Long 0 ;
SavePos BMOFF 0 ;
Math BMS -= 16 ;
Set NAME String FNP ;
String NAME += LNP ;
String NAME += EXT1 ;
Log NAME BMOFF BMS 0 0 ;
Math BMOFF += BMS ;
GoTo BMOFF 0 ;
Get ID Byte 0 ;
Get CTS Long 0 ;
Math CTS -= 16 ;
SavePos CTOFF 0 ;
Math CTOFF += 11 ;
Set NAME String FNP ;
String NAME += LNP ;
String NAME += EXT2 ;
Log NAME CTOFF CTS 0 0 ;
GoTo N 0 ;
Next T ;

```


This is a BMS that will extract the raw bitmap data of each SHP and it's palette. You can use also the .bms file below in MultiEx Commander.
[ssh.zip](https://xentaxbackup.github.io/file/2540_ssh.zip)
## Post #12
- Username: Fatal
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Nov 17, 2009 5:10 am
- Post datetime: 2009-11-22T22:47:23+00:00
- Post Title: Def Jam Fight FOr New York .big

The contents of this post was deleted because of possible forum rules violation.
## Post #13
- Username: Fatal
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Nov 17, 2009 5:10 am
- Post datetime: 2009-11-24T22:31:55+00:00
- Post Title: Def Jam Fight FOr New York .big

Sorry for D posting but..

can someone help me??

I just dont know to open em in PS...

Thank you in advance
## Post #14
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-03-03T21:41:57+00:00
- Post Title: Def Jam Fight FOr New York .big

> Reply from Mr.Mouse ↑Fri Nov 20, 2009 4:42 am at Fri Nov 20, 2009 4:42 am
>
> 
Code: Select allIDString 0 "SHPS";
Get AS Long 0 ;
Get FN Long 0 ;
GetDString FNP 4 0 ;
Set EXT1 String ".bitmap" ;
Set EXT2 String ".colours" ;
For T = 1 To FN ;
GetDString LNP 4 0 ;
Get OFF Long 0 ;
SavePos N 0 ;
GoTo OFF 0 ;
Get ID Byte 0 ;
Get BMS Byte 0 ;
Get B Byte 0 ;
Math B *= 256 ;
Math BMS += B ;
Get B Byte 0 ;
Math B *= 65536 ;
Math BMS += B ;
Get W Int 0 ;
Get H Int 0 ;
Get U1 Long 0 ;
Get U1 Long 0 ;
SavePos BMOFF 0 ;
Math BMS -= 16 ;
Set NAME String FNP ;
String NAME += LNP ;
String NAME += EXT1 ;
Log NAME BMOFF BMS 0 0 ;
Math BMOFF += BMS ;
GoTo BMOFF 0 ;
Get ID Byte 0 ;
Get CTS Long 0 ;
Math CTS -= 16 ;
SavePos CTOFF 0 ;
Math CTOFF += 11 ;
Set NAME String FNP ;
String NAME += LNP ;
String NAME += EXT2 ;
Log NAME CTOFF CTS 0 0 ;
GoTo N 0 ;
Next T ;


This is a BMS that will extract the raw bitmap data of each SHP and it's palette. You can use also the .bms file below in MultiEx Commander.

I tried your bms-script with ssx 3 .ssh files....sadly to no effect :-/
Could you have a look at the and See if they are similar?
Help would be much appretiated!
I've uploaded some Samples here:
[viewtopic.php?f=16&t=21408](https://forum.xentax.com/viewtopic.php?f=16&t=21408)
## Post #15
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-03-04T13:25:40+00:00
- Post Title: Def Jam Fight FOr New York .big

I was only able to grab the Load0.ssh from the movies folder so far:


 DefJam_SSH.zip
.ssh .bitmap .colours (6.03 KiB) Downloaded 19 times



I got a small .bitmap and a 0kb .colours file that i cant seem to open. I couldnt even get stuff with texture finder...
...im after def jams color-palettes.
Any of you guys had success so far?
