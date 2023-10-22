## Post #1
- Username: themonkeyman
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Nov 27, 2009 8:49 am
- Post datetime: 2009-11-27T18:53:50+00:00
- Post Title: Twisted Metal 2 .tpc .dpc

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-28T09:24:12+00:00
- Post Title: Twisted Metal 2 .tpc .dpc

```
Set J Long 8 ;
GoTo J 0 ;
Get Date Long 0 ;
Get FN Long 0 ;
SavePos FS 0 ;
Set EXT String ".tim" ;
For T = 1 To FN ;
Get Size Long 0 ;
SavePos TIMOFF 0 ;
Set Name String T ;
String Name += EXT ;
Log Name TIMOFF Size 0 0 ;
Math FS += Size ;
Math FS += 4 ;
GoTo FS 0 ;
Next T ;

```


This BMS will extract the tim files. 

Use the compiled version in MultiEx Commander :


 tpc.zip
(304 Bytes) Downloaded 49 times



The format of the .TPC files is simple: 

```

[8]		    Magic Word ("TCPMC/0/0/0")
uint32		File date 
uint32		Number of resources in the archive

// Resource (all follow in order after the header)

uint32		Size of resource
[n]		    TIM file data

```
## Post #3
- Username: themonkeyman
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Nov 27, 2009 8:49 am
- Post datetime: 2011-05-02T09:59:55+00:00
- Post Title: Twisted Metal 2 .tpc .dpc

> Reply from Mr.Mouse
>
> Code: Select allIDString 0 "TCPMC" ;
Set J Long 8 ;
GoTo J 0 ;
Get Date Long 0 ;
Get FN Long 0 ;
SavePos FS 0 ;
Set EXT String ".tim" ;
For T = 1 To FN ;
Get Size Long 0 ;
SavePos TIMOFF 0 ;
Set Name String T ;
String Name += EXT ;
Log Name TIMOFF Size 0 0 ;
Math FS += Size ;
Math FS += 4 ;
GoTo FS 0 ;
Next T ;


This BMS will extract the tim files. 

Use the compiled version in MultiEx Commander :
tpc.zip

The format of the .TPC files is simple: 
Code: Select all// Header

[8]		    Magic Word ("TCPMC/0/0/0")
uint32		File date 
uint32		Number of resources in the archive

// Resource (all follow in order after the header)

uint32		Size of resource
[n]		    TIM file data

It's great that you put an ad in your post telling me to contribute regularly, and I plan to.

I want to make a Hex editing tutorial using THPS3/ TM1/TM2 as my example games.

I'm just trying to get more exposure for my mods, which I have made a thread for in another forum.

TM2 uses .DPC files as 3d model containers.

.DMD is the PS1 container format.

The 3d data is "virtually" identical.

[http://www.youtube.com/watch?v=F25WZNAkXWM](http://www.youtube.com/watch?v=F25WZNAkXWM)

Some guy over at TMAlliance already made a tool to view the 3d models!

I just need the guy to send me his tool!
## Post #4
- Username: Kaka
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 05, 2012 12:36 am
- Post datetime: 2012-01-04T16:39:47+00:00
- Post Title: Twisted Metal 2 .tpc .dpc

any1 have BMS script for .tim files ? the one above dont work
