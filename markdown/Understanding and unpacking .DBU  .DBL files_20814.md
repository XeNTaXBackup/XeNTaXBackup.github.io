## Post #1
- Username: nuunuu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 16, 2019 11:13 am
- Post datetime: 2019-07-16T04:33:56+00:00
- Post Title: Understanding and unpacking *.DBU > *.DBL files

Hello!

I've been doing some research on a package format that seems to consist of a *.DBU file created from something called DBL Merge and the internal DBL files that were merged. There hasn't been a lot of widespread attention to this particular format as the format happens to coincide with a couple niche games. These games seem to be specific to one particular game studio - Avalanche Software (not to be confused with Avalanche studios) - credit to ElephantKilla for pointing that out [in this thread](https://forum.xentax.com/viewtopic.php?t=16052). So far, the following games have been confirmed to use this system - Tak and the Power of Juju, Dragon Ball Z: Sagas, Chicken Little, 25 to Life.

I found [this video](https://www.youtube.com/watch?v=ujSHzk40yso) posted by nekorun back in 2016 where it was claimed he was able to open the *.DBU file in a text editor and modify certain config values to mod DBZ: Sagas. In 2018 the same user Nekorun created [this thread](https://zenhax.com/viewtopic.php?t=7445) in ZenHAX asking about how to unpack *.DBU files. Aluigi, admin of ZenHAX and creator of QuickBMS, created a QuickBMS script to that was able to unpack the *.DBU files into a file structure. Aluigi also briefly looked into the *.DBL file, but on discovering they were different from the *.DBU stated - "This is a completely different format and it's crap". He posted some debug log scripts for Nekorun to try and figure out the DBL files himself. I got in contact with Nekorun who told me he wasn't able to figure out the *.DBL extension. Regarding the mods made in the youtube video, I've discovered the text configurable scripts inside of the *.DBU file tend to be located in a "var" folder and use the extension *.dv. These tend to contain settings regarding hit box, gravity, damping, mass, etc. The dbz: sagas video explores a good set of those variables and they appear to be somewhat consistent between games (having looked into the *.dv files in Tak). 

I've recently discovered another post from [this thread](https://forum.xentax.com/viewtopic.php?f=16&t=7081&hilit=.dbl) started back in 2011 by user tuckdragon which was subsequently brought back to life in 2018 by user Elephantkilla (same user that pointed out avalanche software). In that thread, he discovered a couple things about *.DBL files. 

Despite listing *.TGA all over the hex code of the file, the actual textures seem to be stored as *.BMP.
There was one *.DBL file that appeared to actually match the syntax of a *.DBU file (misnaming by a developer?)
He was successfully able to extract textures from a *.DBL using Console Texture Explorer (see page 3 on the aforementioned thread for settings)


So huge props to Elephantkilla who may have done the most work on this file type. 

Anyway, I've been all over the internet looking for info on this file so I thought I would make a thread trying to consolidate all of the hard work that has gone into this file for future users and people researching these games. 

My original goal was to see if I could create a quickBMS script to extract the *.DBL files, but seeing as Elephantkilla was able to extract textures specifically, I may abandon the BMS goal and try to use one of the gui tools listed in the thread he was posting in to try and do the same for another game. Anyone interested in the *.DBL files should post here so that we might pool our work together, but to anyone that has more experience than myself in reverse engineering, which is to say none at all, I would greatly appreciate your input and any advice you may have to offer. 

Most of the threads I linked have some sample *.DBL files, but I can post one if need be. 

Anyway, thanks to anyone who stuck through to the end. I'll update the thread with anything I find.
## Post #2
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2019-07-16T15:46:06+00:00
- Post Title: Understanding and unpacking *.DBU > *.DBL files

Hello, I support the topic. For years I have been looking for ways to manage this archive. I will be glad to any help.
I partially unpacked the archive of two locations from the game 25 to life. Read the information inside the archive.
[https://drive.google.com/open?id=1h3ZKe ... V1WnISByLM](https://drive.google.com/open?id=1h3ZKejNHzsJeEUY6LBQG61V1WnISByLM)

The analysis of files for a map Beatdown assumed by me

```
file (_00000003 - 3D meshes
file NAME - BMP textures
file NAME_00000001 - index meshes or textures UVMapping IDK
file (_00000001 - ambient anim
file (_00000002 - idk
file 2 - some meshes, trigger boxes
```
## Post #3
- Username: Clash
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 04, 2021 3:06 am
- Post datetime: 2021-11-05T21:01:12+00:00
- Post Title: Understanding and unpacking *.DBU > *.DBL files

> Reply from Elephantkilla ↑Tue Jul 16, 2019 11:46 pm at Tue Jul 16, 2019 11:46 pm
>
> 
Hello, I support the topic. For years I have been looking for ways to manage this archive. I will be glad to any help.
I partially unpacked the archive of two locations from the game 25 to life. Read the information inside the archive.
I was trying to get files and it got the same dbl, its from the same developer, sadly the script dont work with everything, I found in a preload txt that at least in the game I want, it has mdb for models
