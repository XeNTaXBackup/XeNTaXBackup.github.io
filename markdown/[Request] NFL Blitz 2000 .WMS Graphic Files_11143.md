## Post #1
- Username: Jaker3
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 19, 2014 12:13 am
- Post datetime: 2014-01-18T18:59:30+00:00
- Post Title: [Request] NFL Blitz 2000 .WMS Graphic Files

Hello,

I was wondering if anyone had any information on .WMS files found in NFL Blitz and NFL Blitz 2000.
Developers: Midway Games and Point of View, INC
The file format is the same on every platform for the game (Dreamcast, PC and N64 versions all contain .WMS files). 

What I would like to be able do: Replace menu graphics and player profiles with newer ones. 

My Story:
Currently I run NflBlitzFans.com and I'm developing a roster manager for NFL Blitz 2000 so people can play the game with 2014's roster. The roster manager can 
change player skin color 
first and last name
jersey number 
On both Dreamcast and N64
I think it would be nice to have an updated menu screen and updated player profile pictures to go with it. 

Any kind of help is appreciated and I've attached a zip with example .WMS files in it.

Thanks,
Jake
[NFL BLitz 2000 WMS FIles.zip](https://xentaxbackup.github.io/file/6926_NFL BLitz 2000 WMS FIles.zip)
## Post #2
- Username: Jaker3
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 19, 2014 12:13 am
- Post datetime: 2014-01-20T17:12:18+00:00
- Post Title: [Request] NFL Blitz 2000 .WMS Graphic Files

Alright so I compared the PC game versus the Dreamcast game and noticed that the Dreamcast game contains PVR files while the PC game does not. I also noticed that for every PVR file the Dreamcast has the PC version has a matching WMS file. SO I'm guessing these WMS files are models with the PVR in them? Any tools you guys think I can check out that would be able to tell if the WMS file is a model? 

I've attached the Dreamcast PVR's with the matching PC WMS for you guys to look at, any help is appreciated. Thanks!
[PVR and WMS files.zip](https://xentaxbackup.github.io/file/6933_PVR and WMS files.zip)
## Post #3
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-01-20T18:24:07+00:00
- Post Title: [Request] NFL Blitz 2000 .WMS Graphic Files

This is what I was able to figure out:
WMS files are nothing more than texture files, they have a 40 byte header and use either RGB565 or RGBA4444 pixel formats. They also sometimes have mipmaps at the bottom.
PVR are texture files too, they have a 16 byte header and use RGB565 or RGBA4444 pixel formats but they can also use compression. PVR files are frequently used by various Dreamcast games.

I recommend TextureFinder for looking through binary data to find images and PVR Viewer for viewing Dreamcast's PVR files.
