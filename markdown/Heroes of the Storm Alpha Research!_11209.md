## Post #1
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-02-15T17:27:05+00:00
- Post Title: Heroes of the Storm Alpha Research!

Greetings,

so Heroes of the Storm Alpha Client is out, I want to start the Research here.

Right now, the Format is changed from MPQ to a unknown Format.

There are tons of DATA Files from data.000 to data.if1 same with a DATA.SMEM

The Folder above contain some INDEX Files.

The only way I know, is to open the .000 with a ISO Editor (which is working slightly). Image Recovery find some OGG / WAV  Files. But that are usless, as this Files are ~ 600 MB which isn't sure the correct File.

Download can be found here:

[https://mega.co.nz/#!zEEkTCIK!zDGxmcRRn ... E28frJmQeg](https://mega.co.nz/#!zEEkTCIK!zDGxmcRRnAZ0Yp6aYCehv23PjD-DkE8JRE28frJmQeg)

[http://www.magnetdl.com/file/1062931/he ... ha-client/](http://www.magnetdl.com/file/1062931/heroes-of-the-storm-alpha-client/)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-02-15T20:16:28+00:00
- Post Title: Heroes of the Storm Alpha Research!

its zlib compressed chunks.
## Post #3
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2014-02-16T13:20:30+00:00
- Post Title: Heroes of the Storm Alpha Research!

chroxx what does it mean when some files are zlib compressed? that they are impossible to extract? because ive seen it on some threads mentioned and then everyone drops interest
## Post #4
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-02-16T13:45:02+00:00
- Post Title: Heroes of the Storm Alpha Research!

Zlib is normaly just Winrar/7zip as I understood.

But that isn't working. MMO Champion got it, as we see, but no Idea  how to continue!
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-02-16T13:47:52+00:00
- Post Title: Heroes of the Storm Alpha Research!

run offzip on the file.
offzip.exe -1 -a c:\file.dat c:\extract_folder 0
then run a file scan program on the dat file you get like
[blog/?p=62](http://forum.xentax.com/blog/?p=62)
## Post #6
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-02-16T18:03:31+00:00
- Post Title: Heroes of the Storm Alpha Research!

NVM. j ust not use the 2 GB big file
## Post #7
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-05-10T10:15:58+00:00
- Post Title: Heroes of the Storm Alpha Research!

Alright, finally decided to check into this.. happy to actually find something usefull here 

I ran the extract command ( offzip.exe -1 a "data.000" "d:\extracted" 0)

got a huge file with a dat extension

run the Jaeder Naub tool

but... how did you get that Nova model ? -> never mind   it is just a texture, anyone found the models ?

T.
## Post #8
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-07-06T12:15:29+00:00
- Post Title: Heroes of the Storm Alpha Research!

Hey guys I found a CASC Explorer for Warlords Of Draenor and also a C# script that extracts objects from the these new CASC files.

So I extracted all the dds files and the M3 files from it and succeeded in writing an import script for 3DS Max.(download in attachment)

The script imports the models in submeshes, bones, skins and even uses the StarCraft 2 Art Tools attachments( so you need to have the Art Tools installed, if you don't just remove these lines from the script )

But now I'm bumping into the animations :/ I'm not that good in understanding and extracting animation information...

So some help would be appreciated.

T.
[HotS m3 import.zip](https://xentaxbackup.github.io/file/7550_HotS m3 import.zip)
## Post #9
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-07-06T12:18:26+00:00
- Post Title: Heroes of the Storm Alpha Research!

Here is a model example

T.
[Storm_Pet_AbathurLocust_Base.zip](https://xentaxbackup.github.io/file/7551_Storm_Pet_AbathurLocust_Base.zip)
## Post #10
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2014-07-06T18:50:11+00:00
- Post Title: Heroes of the Storm Alpha Research!

> Reply from TaylorMouse
>
> Hey guys I found a CASC Explorer for Warlords Of Draenor and also a C# script that extracts objects from the these new CASC files.

So I extracted all the dds files and the M3 files from it and succeeded in writing an import script for 3DS Max.(download in attachment)

The script imports the models in submeshes, bones, skins and even uses the StarCraft 2 Art Tools attachments( so you need to have the Art Tools installed, if you don't just remove these lines from the script )

But now I'm bumping into the animations :/ I'm not that good in understanding and extracting animation information...

So some help would be appreciated.

T.
Could you share or link to the script to extract the CASC files?
Thanks.
## Post #11
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-07-06T20:48:54+00:00
- Post Title: Heroes of the Storm Alpha Research!

Sure man

[https://github.com/tomrus88/CASCExplorer](https://github.com/tomrus88/CASCExplorer)

T.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-07-06T22:25:44+00:00
- Post Title: Heroes of the Storm Alpha Research!

Walk animation of Storm_Pet_AbathurLocust_Base.m3, 0xC140 Walk_full

For .x animation files the frame count for each bone normally is the same
but for the Storm_Pet .m3 file it is not.
Each bone should have a table for his positions and one for his rotations
but here it seems to be 11 tables (pos) versa 18 tables (rot).

So I don't get it since from your script the pet seems to have 19 bones.


(Following data maybe faulty since it was derived manually.)

0xC200  unknown Array of 11 x 8 DWords
(each 1st and 6th value is the frame count, 5th value is the maximum frame time offset)

11 tables (for 11 bones?) to follow:

1. table, 0xC360 33 frame time offsets [ms?]
0 33 66 100 133 166 200 233 266 300 333 366 400 433 466 500 
533 566 600 633 666 700 733 766 800 833 866 900 933 966 1000 1033 1066

0xC3F0 33 frames x 12 bytes (3 floats, position?)

 1. 0000 -0.042748 -0.050062 0.436773 
 2. 0033 -0.041306 -0.043050 0.440469 
 3. 0066 -0.037569 -0.036517 0.437106 
...
31. 1000 -0.038585 -0.065343 0.429404 
32. 1033 -0.041611 -0.057529 0.438589 
33. 1066 -0.042748 -0.050062 0.436773 


2nd table, 0xC580 31 frame time offsets
C600 31 x 12

C780 3 tables with 2 frames each

6th table, 0xC810 33
C8A0 33 x 12

CA30 29
CAB0 29 x 12

CC10 28
CC80 28 x 12

9th table, 0xCDD0 11 frame time offsets
CE00 11 x 12

CE90 2 tables with 2 frames each

------------------------------

0xCEF0  unknown Array of 18 x 8 DWords
(each 1st and 6th value is the frame count, 5th value is the maximum frame time offset)

18 tables (for 18 bones?) to follow:

1st table, 0xD130  32 frame time offsets
0 33 66 100 133 166 200 233 266 300 333 366 400 433 466 500 
533 566 600 633 666 700 733 766 800 833 866 900 933 1000 1033 1066 

0xD1B0 -  D3B0  32 frames x 16 bytes (4 floats, rotation?)
 1. 0000 0.168332 -0.000626 0.006733 0.985707 
 2. 0033 0.180361 -0.001735 0.002054 0.983597 
 3. 0066 0.190348 -0.002788 -0.003073 0.981708 
...
30. 1000 0.154780 0.001649 0.012016 0.987874 
31. 1033 0.161377 0.000429 0.009110 0.986851 
32. 1066 0.168332 -0.000626 0.006733 0.985707

2nd table, 0xD3B0 21 
D410 21 x 16

D560 41
D610 41 x 16

D8A0 39
D940 39 x 16

DBB0 39
DC50 39 x 16

DEC0 41
DF70 41 x 16

E200 45
E2C0

E590 45
E650

E920 44
E9D0

10th table, 0xEC90 40
ED30

EFB0 24
F010

F190 16
F1D0 

F2D0 27
F340

F4F0 22
F550 

F6B0 15
F6F0 

F7E0 18
F830

F950 15
F990

18th table, 0xFA80 15 frame time offsets
FAC0 15 frames x 16 bytes (4 floats, rotation?)

------------

0xFBB0 8 unknown DWords
(1st and 6th value is the frame count, 5th value is the maximum frame time offset)

FBD0  27 frame time offsets
FC40 - FF34  756 = 63 * 12 (?)
-------------------------------------

Once we know which table is belonging to which bone you could use the frame counts in the 
arrays at 0xC200, 0xCEF0 for your script.
## Post #13
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-07-25T15:30:23+00:00
- Post Title: Heroes of the Storm Alpha Research!

This I found through one of my buddies on SC2Mapster:

[https://github.com/flo/m3addon/blob/mas ... ctures.xml](https://github.com/flo/m3addon/blob/master/structures.xml)

But I can't figure out how to convert the content of the m3 file into descent MAX animations ...

T.
## Post #14
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-07-28T13:20:59+00:00
- Post Title: Heroes of the Storm Alpha Research!

> Reply from TaylorMouse
>
> This I found through one of my buddies on SC2Mapster:

https://github.com/flo/m3addon/blob/mas ... ctures.xml

But I can't figure out how to convert the content of the m3 file into descent MAX animations ...

T.Hello my friends, how to use this software "CASC Explorer", thank you very much for your help.
## Post #15
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2014-11-10T19:26:45+00:00
- Post Title: Heroes of the Storm Alpha Research!

Try to use CASCExplorer, but got error - "Error Initializing required data files".
As I understand, it happens, because done for latest WoW addons, which has this new filesystem.

Be glad if anyone introduce how to use it on Heroes of the Storm for archive extraction. (plus what means <pattern>, <destination> and <locale> for CASCConsole)
## Post #16
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-01-08T20:55:17+00:00
- Post Title: Re: Heroes of the Storm Alpha Research!

Hi guys,

there is a new version of Heroes of the Storm Alpha (build 33353)

up till now, I am still not able to import the animations :/

I've been reading up on a lot of stuff, I think I have everything in there, but still I 'm to stupid to figure out the animation stuff.... :'(

I cut this script into 2 bits
1. import  m3 model, up till now, I think all of the models import ( SC2 and Heroes )
2. import  animation ( not complete )

Don't forget to change the Texture path in the script if you want to import the textures


T.
[HotS m3 import.rar](https://xentaxbackup.github.io/file/8454_HotS m3 import.rar)
## Post #17
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-01-08T20:57:27+00:00
- Post Title: Re: Heroes of the Storm Alpha Research!

This is the animation import

it is not a utility yet, so you need to scroll down and change the filename that you want to import

it does not import the mesh, but it does import the bones ( uncomment the BuildBones() line)

I would appreciate the help, since I've put too many hours and nights into this to let it slip :/

Much appreciated!

T.
[AnimationImport.rar](https://xentaxbackup.github.io/file/8455_AnimationImport.rar)
## Post #18
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-01-08T20:58:49+00:00
- Post Title: Re: Heroes of the Storm Alpha Research!

Here is the model that I refer to in the Animation Import script

T.
[Storm_Minion_KingsCrest_Wizard.rar](https://xentaxbackup.github.io/file/8456_Storm_Minion_KingsCrest_Wizard.rar)
