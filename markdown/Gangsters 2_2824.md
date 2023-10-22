## Post #1
- Username: Sarmatii
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 19, 2007 3:25 am
- Post datetime: 2007-10-19T08:00:49+00:00
- Post Title: Gangsters 2

Anyone ever played [Gangsters 2](http://en.wikipedia.org/wiki/Gangsters_2)?

It got great Isometric pixel-made graphics suitable for hobbyist game making and modding.

can you support this game for you software please?
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-10-19T13:23:26+00:00
- Post Title: Gangsters 2

Attach a sample please (but not Rapidshare/Megaupload/depositfiles or filefactory) try zshare.net or divshare.com

Thanks
## Post #3
- Username: Sarmatii
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 19, 2007 3:25 am
- Post datetime: 2007-10-19T17:42:58+00:00
- Post Title: Gangsters 2

Oh Great and NO thank YOU!!!  

and because I just got dial-up internet (  ) it may take a day for me to upload it. but i'll upload it! be sure and await. and is just one sample enough? (each are 8 megs) or it should be 2 of them?  

and thank you again for fast responding
## Post #4
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-19T19:08:38+00:00
- Post Title: Gangsters 2

> Reply from Sarmatii
>
> Oh Great and NO thank YOU!!!  

and because I just got dial-up internet (  ) it may take a day for me to upload it. but i'll upload it! be sure and await. and is just one sample enough? (each are 8 megs) or it should be 2 of them?  

and thank you again for fast responding

I have got the game to with 1MBit upload, just tell me which files you want uploaded.
## Post #5
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-19T19:17:56+00:00
- Post Title: Gangsters 2

Installed the game to help out. The files are available from:


 Filename  Filesize     Downloadlink 
 Set1.rar   15.64 MB  [http://uploaded.to/?id=ajdi7r](http://uploaded.to/?id=ajdi7r) 
 Set2.rar   15.54 MB  [http://uploaded.to/?id=nx1flw](http://uploaded.to/?id=nx1flw) 
 Set3.rar   15.64 MB  [http://uploaded.to/?id=ebu9h7](http://uploaded.to/?id=ebu9h7)
## Post #6
- Username: Sarmatii
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 19, 2007 3:25 am
- Post datetime: 2007-10-20T05:42:05+00:00
- Post Title: Gangsters 2

OH!! you're GREAT!! thank you! hate those who say Europeans are bad peoples! LOL
## Post #7
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-20T11:24:37+00:00
- Post Title: Gangsters 2

> Reply from Sarmatii
>
> OH!! you're GREAT!! thank you! hate those who say Europeans are bad peoples! LOL

Your welcome
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-09T23:27:24+00:00
- Post Title: Gangsters 2

> Reply from NKCSS
>
> Installed the game to help out. The files are available from:


 Filename  Filesize     Downloadlink 
 Set1.rar   15.64 MB  http://uploaded.to/?id=ajdi7r 
 Set2.rar   15.54 MB  http://uploaded.to/?id=nx1flw 
 Set3.rar   15.64 MB  http://uploaded.to/?id=ebu9h7
Don't exist anymore.
## Post #9
- Username: Stauricus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 10, 2007 9:30 pm
- Post datetime: 2007-11-10T20:21:13+00:00
- Post Title: Gangsters 2

i've uploaded the 1st file from my pc
if  need the other files, just tell me  

i'm looking forward for these graphics too   


[http://www.zshare.net/download/4808393c51df73/](http://www.zshare.net/download/4808393c51df73/)   (16 MB)
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-14T05:10:09+00:00
- Post Title: Gangsters 2

Support for it isn't easy. There doesn't seem to be a directory.
Reversed the exe a bit, this is what I got so far(don't know if this is of any help):

```
//--- 010 Editor v2.1.3 Binary Template
//
// File:
// Author:
// Revision:
// Purpose:
//--------------------------------------
local int i;

uint magic;
uint uk1; // seems to be just skipped
uint offset;
FSeek(offset);
uint uk1;
short uk2;
short uk3;
uint uk4;
uint uk5;
uint uk6;
struct UK7
{
	uint uk1;
	uint uk2;
}uk7[uk4];

byte uk8[uk4]; // uk4 * 1 byte

struct UK9
{
	uint uk1;
	uint uk2;
} uk9[uk5];

byte uk10[uk6]; // 1 * uk6 bytes

/* this is done inside the exe
if(uk4 != 0)
{
	for(i=0; i<uk4; i++)
	{
		uk7[i].uk2 += &uk10
		uk7[i].uk1 = uk9[uk7[i].uk1];
	}
}
*/

uint uk11;
uint uk12;

/* only allocated in memory and constructors called uk12 * 16 bytes
struct UK13
{
	uint uk1;
	uint uk2;
	uint uk3;
	uint uk4;
} uk13[uk12];
*/

struct UK16
{
	uint uk14; // var_2C
	uint uk15[uk14];
} uk16[uk12]<optimize=false>;
```
