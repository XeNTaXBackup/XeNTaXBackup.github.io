## Post #1
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-08-09T21:26:36+00:00
- Post Title: 3D models behind a .pat file

I want convert a 3D model from a android game,
So i have estracted all the contenent, and i find 
The models, but is in to a .pat file, like almost other files
On the game files folder... he looks like a sort of zipped file.
I attach a model file of the game.

Also i find a "patches.txt" file that contains  a file list,
Here the row of the file attached at this post:

    Char/Monster/Spa/Mon_Gumuri,11

Hope these help to find the key to open it.
[Mon_Gumuri.zip](https://xentaxbackup.github.io/file/11526_Mon_Gumuri.zip)
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-08-09T21:34:26+00:00
- Post Title: 3D models behind a .pat file

The file is compressed or encrypted, not zlib though.
## Post #3
- Username: Smakkohooves
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-08-09T22:39:22+00:00
- Post Title: 3D models behind a .pat file

[http://aluigi.altervista.org/bms/unity3d_webplayer.bms](http://aluigi.altervista.org/bms/unity3d_webplayer.bms)
## Post #4
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-08-10T10:17:10+00:00
- Post Title: 3D models behind a .pat file

> Reply from chrrox
>
> http://aluigi.altervista.org/bms/unity3d_webplayer.bms
I have no pratice with those things, you have tried it and works?
What i have to do with that file?(bms)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-10T13:44:36+00:00
- Post Title: 3D models behind a .pat file

google for quickbms.exe

when clicking on the exe (in the windows explorer) it prompts you for selecting 
the BMS script
the input archive to extract
the output folder

This is a [hex2obj] created mesh found in the extracted file:



CAB-06DA35_.jpg (102.28 KiB) Viewed 90 times


Seems there's also a skeleton contained.
## Post #6
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-08-11T01:52:09+00:00
- Post Title: 3D models behind a .pat file

I do something wrong maybe....
I continue to try.

This can works also with the texture files?
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-11T03:24:10+00:00
- Post Title: 3D models behind a .pat file

after you extract CAB-06da3511b78f80945a7d37cb688d6b61 from Mon_Gumuri.pat 
you can open it with "Unity Studio" to export the mesh and textures from it   
[viewtopic.php?f=10&t=11807](http://forum.xentax.com/viewtopic.php?f=10&t=11807)
## Post #8
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-08-12T00:59:50+00:00
- Post Title: 3D models behind a .pat file

1)open quickbms. Ok
2)select .mbs. Ok
3)open file (.pat) OK 
4)Save output...

" Error: Invalid command "name" or arguments -1 at line 1 "

Why?
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-12T02:02:52+00:00
- Post Title: 3D models behind a .pat file

i have no idea what that error means but here is the quickbms script
if yours has html or something in it after saving from the webpage  


 unity3d_webplayer.zip
(613 Bytes) Downloaded 17 times


tested on QuickBMS 0.7.3 and 0.7.5 and all is working
## Post #10
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-08-12T04:33:02+00:00
- Post Title: 3D models behind a .pat file

> Reply from AceWell
>
> i have no idea what that error means but here is the quickbms script
if yours has html or something in it after saving from the webpage  
unity3d_webplayer.zip
tested on QuickBMS 0.7.3 and 0.7.5 and all is working
Ups, i think have make a bad BMS, now it works fine  

Thanks again! So now i try to use it with that unity studio.
## Post #11
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2016-08-13T14:33:52+00:00
- Post Title: 3D models behind a .pat file

Sorry for so stupid question,but what game is this?
## Post #12
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-08-13T19:37:20+00:00
- Post Title: 3D models behind a .pat file

> Reply from Rutabaga
>
> Sorry for so stupid question,but what game is this?
Keroro action hero for kakao 
It's a korean game.

I have problems with unity studio, 
the exe dont' run on my pc, someone know some alternatives?
