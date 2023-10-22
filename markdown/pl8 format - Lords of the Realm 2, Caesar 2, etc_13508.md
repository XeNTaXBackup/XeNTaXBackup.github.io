## Post #1
- Username: DrAsik
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 18, 2012 12:12 pm
- Post datetime: 2015-11-07T22:57:20+00:00
- Post Title: pl8 format - Lords of the Realm 2, Caesar 2, etc

Some tips for parsing this one? Pretty sure it's an image format, perhaps a spritesheet. Here are some names and file sizes:



Some files are included for reference.
[Lords of the Realm II.zip](https://xentaxbackup.github.io/file/9978_Lords of the Realm II.zip)
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2015-11-20T06:25:07+00:00
- Post Title: pl8 format - Lords of the Realm 2, Caesar 2, etc

A PL8 file can contain different images:
* ordinary bitmaps (for backgrounds)
* isometric tiles
* run-length encoded sprites

I will see if I can find some detailed info about file format on my PC.
Would some undocumented java source code be useful too?



CASTLE1A.PNG (130.94 KiB) Viewed 191 times
## Post #3
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2015-11-21T22:20:26+00:00
- Post Title: pl8 format - Lords of the Realm 2, Caesar 2, etc

Here's a half-finished PL8 -> PNG extractor (Eclipse project with java sources):
[https://drive.google.com/file/d/1hCD7RL ... sp=sharing](https://drive.google.com/file/d/1hCD7RL4M9DE7aVv3wJr433P_OZuOe3O5/view?usp=sharing)

The algorithms work but the usability leaves much to be desired.
Arguments and options are hard-coded in Main.java so every time you want to convert another file, you'll have to recompile the project.   I haven't had the time to fix that.

Inside the zip there's also a txt that contains a list of nearly all pl8 files and their corresponding palette and type.
## Post #4
- Username: Alchemist
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 30, 2019 4:40 am
- Post datetime: 2019-12-29T20:57:26+00:00
- Post Title: pl8 format - Lords of the Realm 2, Caesar 2, etc

pl8 Magic can convert them png files. 

Drag and Drop the pl8 and 256 files on the browser.

[https://pl8magic.binaryalchemist.com/](https://pl8magic.binaryalchemist.com/)



pl8Magic.png (120.32 KiB) Viewed 160 times
## Post #5
- Username: H3ll0w33n
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 02, 2022 10:11 pm
- Post datetime: 2022-03-02T14:17:04+00:00
- Post Title: pl8 format - Lords of the Realm 2, Caesar 2, etc

Hello!
I´ve trying to process .pl8 images into bmps. I had success with 1 sprite images, but I had no lucky with multiple sprites .pl8 and also, the links to "tools" you posted here no longer work.
Is there any tool I could use to turn .pl8 + .256 into .bmp? Open source codes would be awesome.
## Post #6
- Username: H3ll0w33n
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-02T19:48:27+00:00
- Post Title: pl8 format - Lords of the Realm 2, Caesar 2, etc

Here is the mirror for Lords2_PL8_Extractor_v0.1.zip

[https://drive.google.com/file/d/1C1SfvA ... sp=sharing](https://drive.google.com/file/d/1C1SfvA6jPiIHoftVLHqcEtDUEWUZAPv_/view?usp=sharing)
## Post #7
- Username: H3ll0w33n
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 02, 2022 10:11 pm
- Post datetime: 2022-03-02T22:19:55+00:00
- Post Title: pl8 format - Lords of the Realm 2, Caesar 2, etc

> Reply from ikskoks ↑Thu Mar 03, 2022 3:48 am at Thu Mar 03, 2022 3:48 am
>
> 
Here is the mirror for Lords2_PL8_Extractor_v0.1.zip

https://drive.google.com/file/d/1C1SfvA ... sp=sharing

Thank you very much man! I spent three days trying to do this!
## Post #8
- Username: Prokuneo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jul 22, 2022 7:50 pm
- Post datetime: 2022-07-22T15:49:39+00:00
- Post Title: pl8 format - Lords of the Realm 2, Caesar 2, etc

> Reply from herbert3000 ↑Sun Nov 22, 2015 6:20 am at Sun Nov 22, 2015 6:20 am
>
> 
Here's a half-finished PL8 -> PNG extractor (Eclipse project with java sources):
https://drive.google.com/file/d/1hCD7RL ... sp=sharing

The algorithms work but the usability leaves much to be desired.
Arguments and options are hard-coded in Main.java so every time you want to convert another file, you'll have to recompile the project.   I haven't had the time to fix that.

Inside the zip there's also a txt that contains a list of nearly all pl8 files and their corresponding palette and type.

Hi, sorry to reopen this old topic, but I've been interested in making a LOTR2 remake for myself, (and with the permission of its creators, for the public), remaking each sprite in higher resolution, but the biggest obstacle I have now is this conversion from PL8 to PNG (and vice versa), could you please explain how it is done? I already installed Eclipse IDE for Java Developers and Eclipse Modeling Tools, although they look identical to me I have no idea how they operate and how to make the project that you kindly shared here work. I'm not a programmer, but a graphic designer.

This is an example of what I want to do, I got the png thanks to the post here where you shared it.
## Post #9
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2022-07-23T00:33:52+00:00
- Post Title: pl8 format - Lords of the Realm 2, Caesar 2, etc

Hey Prokuneo, that looks fantastic!

However, I see a few obstacles:
- At the moment we only have a PL8 to PNG converter but no tool to repack the PNGs back into a PL8.
- Even if we had a PNG to PL8 converter, the dimensions of the modified tiles would have to match the dimensions of the original tiles.
- Without modification of the the game's code, it will only run in 640x480.

I think I could help with the first issue.
Maybe the admin of the LotR2 discord server could modify the executable to allow a higher resolution: [https://discord.gg/P68BSne](https://discord.gg/P68BSne)

I've uploaded a compiled version of the extractor here:
[https://retrogamesvault.com/lords2/file ... ractor.zip](https://retrogamesvault.com/lords2/files/Lords2_PL8Extractor.zip)
## Post #10
- Username: Prokuneo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jul 22, 2022 7:50 pm
- Post datetime: 2022-07-23T01:10:22+00:00
- Post Title: pl8 format - Lords of the Realm 2, Caesar 2, etc

> Reply from herbert3000 ↑Sat Jul 23, 2022 8:33 am at Sat Jul 23, 2022 8:33 am
>
> 
Hey Prokuneo, that looks fantastic!

However, I see a few obstacles:
- At the moment we only have a PL8 to PNG converter but no tool to repack the PNGs back into a PL8.
- Even if we had a PNG to PL8 converter, the dimensions of the modified tiles would have to match the dimensions of the original tiles.
- Without modification of the the game's code, it will only run in 640x480.

I think I could help with the first issue.
Maybe the admin of the LotR2 discord server could modify the executable to allow a higher resolution: https://discord.gg/P68BSne

Thank you very much, it means a lot to me.

To adjust the resolution, I had thought of modifying the SIERRA.INF file or the .CFG file as necessary (if it has one, I have not thoroughly reviewed it), the SIERRA.INF file has this section, so in "theory" should force the display of the tiles to the new size they will have, but this is a test that could only be done when you have PL8 files that contain tiles of 354 pixels wide, in the same way I will contact the admin you mention and maybe there is a viable technical solution. Again, thank you very much.

[Requirements]
SetupVer=3.2.2.1
Colors=256
ScreenWidth=640
ScreenHeight=480
VideoSpeed=0
Wave=1
MIDI=0
CDROM=2
MemKB=0
PhysicalMem=7700
CPU=486-66
Joystick=0
Printer=0
WinVer=395
## Post #11
- Username: jballou
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 15, 2022 6:05 am
- Post datetime: 2022-09-14T22:09:17+00:00
- Post Title: pl8 format - Lords of the Realm 2, Caesar 2, etc

> Reply from Prokuneo ↑Fri Jul 22, 2022 11:49 pm at Fri Jul 22, 2022 11:49 pm
>
> 
Hi, sorry to reopen this old topic, but I've been interested in making a LOTR2 remake for myself, (and with the permission of its creators, for the public), remaking each sprite in higher resolution, but the biggest obstacle I have now is this conversion from PL8 to PNG (and vice versa), could you please explain how it is done? I already installed Eclipse IDE for Java Developers and Eclipse Modeling Tools, although they look identical to me I have no idea how they operate and how to make the project that you kindly shared here work. I'm not a programmer, but a graphic designer.

This is an example of what I want to do, I got the png thanks to the post here where you shared it.

I have looked at doing as simple a remake as possible of LOTR2 in another engine about 50 times, but it's just such a pile of work. Are you doing a straight HD upgrade of the art assets, or will there be engine updates as well?
## Post #12
- Username: Prokuneo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jul 22, 2022 7:50 pm
- Post datetime: 2022-09-26T23:34:00+00:00
- Post Title: pl8 format - Lords of the Realm 2, Caesar 2, etc

> Reply from jballou ↑Thu Sep 15, 2022 6:09 am at Thu Sep 15, 2022 6:09 am
>
> 
I have looked at doing as simple a remake as possible of LOTR2 in another engine about 50 times, but it's just such a pile of work. Are you doing a straight HD upgrade of the art assets, or will there be engine updates as well?

What I am trying to do is make a purely visual improvement, which will require some adjustment in the configuration (in theory), only that I am at a standstill since I need a way to convert a single PNG file into a PL8 file to do a technical test, if I could achieve that, I would redesign all the PL8s (which are not few) and then convert them all to PL8 and voilá, but I don't know programming, only graphic design. So, no engine updates from me (or at least, I don't know if it deserves it yet)
