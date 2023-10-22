## Post #1
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2013-07-19T16:11:48+00:00
- Post Title: Judge Dredd: Dredd vs. Death - Text files

Hi,

I want to translate the game Judge Dredd: Dredd vs. Death, i managed to extract and repack the .asr file(evin tool [viewtopic.php?f=33&t=8902&hilit=asura+engine](http://forum.xentax.com/viewtopic.php?f=33&t=8902&hilit=asura+engine)) but i don't know how to edit the localization files (HTXT, LTXT, npct, PCLT and PTXT). Is there a way to edit these files? Thank you.
[Dredd-Text files.rar](https://xentaxbackup.github.io/file/6526_Dredd-Text files.rar)
## Post #2
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2013-07-19T17:30:52+00:00
- Post Title: Judge Dredd: Dredd vs. Death - Text files

Evin has made an editor to the HTXT files for AvP and Sniper Elite V2. Maybe it'll work. 

[viewtopic.php?f=35&t=8648](http://forum.xentax.com/viewtopic.php?f=35&t=8648)
## Post #3
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2013-07-19T17:55:57+00:00
- Post Title: Judge Dredd: Dredd vs. Death - Text files

> Reply from Rion
>
> Evin has made an editor to the HTXT files for AvP and Sniper Elite V2. Maybe it'll work. 

viewtopic.php?f=35&t=8648

Already tried. Doesn't work with this game.
## Post #4
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2013-07-26T13:34:18+00:00
- Post Title: Judge Dredd: Dredd vs. Death - Text files

anyone?
## Post #5
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-07-26T18:16:18+00:00
- Post Title: Judge Dredd: Dredd vs. Death - Text files

send me pm with d link
## Post #6
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2013-07-29T18:44:23+00:00
- Post Title: Judge Dredd: Dredd vs. Death - Text files

> Reply from michalss
>
> send me pm with d link

Done.
## Post #7
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-07-31T15:49:31+00:00
- Post Title: Judge Dredd: Dredd vs. Death - Text files

i have completed 010 template, since im on holiday this week i cannot finish repacker but i will once i get back, so please patient.
## Post #8
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2013-07-31T18:25:51+00:00
- Post Title: Judge Dredd: Dredd vs. Death - Text files

> Reply from michalss
>
> i have completed 010 template, since im on holiday this week i cannot finish repacker but i will once i get back, so please patient.

Ok, i'll wait.
## Post #9
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2013-08-13T04:19:18+00:00
- Post Title: Judge Dredd: Dredd vs. Death - Text files

Any news?
## Post #10
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-08-14T06:24:17+00:00
- Post Title: Judge Dredd: Dredd vs. Death - Text files

OK coz there are 3 dirrefent format i was able to completed Template for all of them, can you please send me more this files at least 3 files from all types ?? I will do repacker first and then packer but it will take some time...

Here is template :

```
//--- 010 Editor v4.0.4a Binary Template
//
// File: 
// Author: michalss
// Revision: 1.0
// Purpose:
//--------------------------------------
LittleEndian();

local int pos,x;
local uint header;

char LTXT[4];
header=ReadUInt(0);

if (header==1415074892) { //this is LTXT
    Printf("This is LTXT!");

uint size;
uint version;
uint zero;
uint count;

for (x=0;x<count;x++) {

   struct TEXT_LTXT { 
    uint tSize;
    char text[tSize*2];
   } Data; 

}


} else if (header==1415074888) {
    Printf("This is HTXT!");

uint size;
uint version;
uint zero;
uint count;

for (x=0;x<count;x++) {

   struct TEXT_HTXT { 
    uint id;
    uint tSize2;
    char text2[tSize2*2];
   } Data; 

}

} else if (header==1415074896) {
    Printf("This is PTXT!");

    uint size;
    uint version;
    uint zero;
    uint GUID;
    uint count;
    char cText[12]; //not sure what this represent??

for (x=0;x<count;x++) {

   struct TEXT_PTXT { 
    //uint id;
    uint tSize2;
    char text2[tSize2*2];
   } Data; 

}

}


```
## Post #11
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2013-08-14T14:28:27+00:00
- Post Title: Judge Dredd: Dredd vs. Death - Text files

> Reply from michalss
>
> OK coz there are 3 dirrefent format i was able to completed Template for all of them, can you please send me more this files at least 3 files from all types ?? I will do repacker first and then packer but it will take some time...

Done.
