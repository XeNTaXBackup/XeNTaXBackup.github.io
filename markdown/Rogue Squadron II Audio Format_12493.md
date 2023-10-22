## Post #1
- Username: iteachvader
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Sep 21, 2014 2:47 am
- Post datetime: 2015-01-10T21:57:15+00:00
- Post Title: Rogue Squadron II Audio Format

I've been trying to rip the sound effects from Rogue Squadron II: Rogue Leader on the Gamecube for an extremely long time now, and have had no progress. I was referred to this forum, and I'm here in hopes of solving this once and for all.

On the Dolphin forums, I was told that the sound files must be in a format that is handled by Dolphin's DSP, and that almost all GC audio formats are handled by a plugin for Winamp. I've tested this and it seems to ring true except with Rogue Squadron II.

I believe the sounds are encrypted in some sort of package or container in the ISO. I've found the file with the sound effects in it, but have no idea how to go about unpacking it, as it is simply a .DAT file that doesn't seem to extract with any programs that I've used on it, including QuickBMS. It can be found easily within the filesystem while in Dolphin, just scroll down until you find data.dat. I can verify that the sound effects are inside the file since when I import it as raw data into Audacity, I can faintly hear them against a strong wall of static. I have no clue how to go about figuring out how to unpack the file, so...

Help!! Does anyone have any info on it?
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-01-13T18:53:40+00:00
- Post Title: Rogue Squadron II Audio Format

Have you tried RogueDat?

[http://www.moddb.com/mods/star-wars-rog ... oguedat-10](http://www.moddb.com/mods/star-wars-rogue-leader-3d/downloads/roguedat-10)
[http://rogue.squadron.tripod.com/download.htm](http://rogue.squadron.tripod.com/download.htm)

Edit
I thought i remembered there being a thread and sure enough there is
[viewtopic.php?f=10&t=6165](http://forum.xentax.com/viewtopic.php?f=10&t=6165)
Aluigi's bms script works on those *.dat files perfectly
## Post #3
- Username: iteachvader
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Sep 21, 2014 2:47 am
- Post datetime: 2015-01-14T02:51:16+00:00
- Post Title: Rogue Squadron II Audio Format

> Reply from AceWell
>
> Have you tried RogueDat?

http://www.moddb.com/mods/star-wars-rog ... oguedat-10
http://rogue.squadron.tripod.com/download.htm

That only works with the PC version of the first Rogue Squadron, not with II or III on GC, but yes I have.
## Post #4
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-04-19T08:50:25+00:00
- Post Title: Rogue Squadron II Audio Format

> Reply from iteachvader
>
> AceWell wrote:Have you tried RogueDat?

http://www.moddb.com/mods/star-wars-rog ... oguedat-10
http://rogue.squadron.tripod.com/download.htm

That only works with the PC version of the first Rogue Squadron, not with II or III on GC, but yes I have.

the script can unpack, PC, and GC version, of .DAT files
but the .DAT files contain any extension for files

i have discover an other guy who's working around those formats:
[http://satd.sk/web/rs/](http://satd.sk/web/rs/)

 source code of Tools:
[https://github.com/dpethes/rerogue](https://github.com/dpethes/rerogue)
## Post #5
- Username: ARAJediMaster
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Jun 12, 2015 12:17 pm
- Post datetime: 2015-06-12T04:26:11+00:00
- Post Title: Rogue Squadron II Audio Format

Well, begging your pardon, CZW, but it may seem like he is getting closer to extracting the sound, as these comments on this forum say here: [https://forums.dolphin-emu.org/Thread-s ... pid=373783](https://forums.dolphin-emu.org/Thread-sfx-ripping-decoding-dumping-features?pid=373783).

I don’t know if he will listen to what’s going on here. He says the .dat files he acquired from the game are especially encoded so that he cannot extract them by ordinary methods. Perhaps that’s why he didn’t answer you.
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-07-07T11:17:15+00:00
- Post Title: Rogue Squadron II Audio Format

```
https://github.com/jackoalan/swrs_musyx/releases
```


Local backup


 swrs_musyx.zip
(39.14 KiB) Downloaded 35 times
