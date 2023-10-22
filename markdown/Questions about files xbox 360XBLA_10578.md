## Post #1
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2013-07-04T16:51:35+00:00
- Post Title: Questions about files xbox 360/XBLA

Friends I have two questions if possible would like to hear you.
After installing some games in HD or download via the XBOX360 Game On Demand (GOD), they generate a sequence of files in a folder, eg.:

Data0001
Data0002
Data0003






This is the structure of the files copied to the hard drive or downloaded Game on Demand.
For the JTAG consoles to explore the contents of files normally inserting MODS and other things, but my console is original would have some tool or some scripts that can do this job.
Wanted to extract the contents of the games and insert back in the same format.
From what I've been researching the reading mode for extraction is the same for all games, then I would wonder how to create a Generic BMS scripts to compress and decompress the files that structure?


The other doubt is, I am wanting to learn to create scripts BMS to help the community, it would be possible, a tutorial using the sample file attached is a game XBLA (Xbox Live Arcade)

```

Offset      0  1  2  3  4  5  6  7   8  9  A  B  C  D  E  F

00000000   44 4E 42 57 00 00 00 2D  00 00 00 2B 00 00 00 34   DNBW...-...+...4
00000010   00 00 00 60 00 00 00 94  00 00 2D 00 00 00 2D 94   ...`...”..-...-”
00000020   00 00 16 E4 00 00 44 78  00 00 78 00 00 00 C0 00   ...ä..Dx..x...À.
00000030   00 EE A0 00 00 09 00 01  00 00 01 E0 4C 6F 63 61   .î ........àLoca
00000040   6C 69 7A 65 64 20 57 61  76 65 20 42 61 6E 6B 00   lized Wave Bank.
00000050   00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................

```

[https://dl.dropboxusercontent.com/u/569 ... andLoc.zip](https://dl.dropboxusercontent.com/u/56928624/LastStandLoc.zip)
How to make the script?
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-07-04T18:26:14+00:00
- Post Title: Questions about files xbox 360/XBLA

Jtag's break the xbox360 EULA. I'd tread lightly here as piracy is a no-no. Edit, my bad, you've legally bought it. sorry for the confusion.
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-07-05T05:12:37+00:00
- Post Title: Questions about files xbox 360/XBLA

Things Needed:
a JTAG
a GOD container of a new game such as Dead Island or Driver San Francisco
wx360 - find on google.com
GoD2ISO - find on google.com

Tutorial:
1: Open GOD2ISO and click add next to God packages, browse inside your GoD folder you'll see a file like this
D664F5CB98F39197BB933A8C2F510839 usually under 60kb (Don't select the Data0001 files)
2: Select an output directory and click go it usually takes about 5-10 mins to make it a ISO
3: Once that's complete open wx360 and open the ISO and extract to external hdd like you would anyother ISO
4: ISO can be read from any ISO mounter
## Post #4
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2013-07-08T19:19:10+00:00
- Post Title: Questions about files xbox 360/XBLA

> Reply from michalss
>
> Things Needed:
a JTAG
a GOD container of a new game such as Dead Island or Driver San Francisco
wx360 - find on google.com
GoD2ISO - find on google.com

Tutorial:
1: Open GOD2ISO and click add next to God packages, browse inside your GoD folder you'll see a file like this
D664F5CB98F39197BB933A8C2F510839 usually under 60kb (Don't select the Data0001 files)
2: Select an output directory and click go it usually takes about 5-10 mins to make it a ISO
3: Once that's complete open wx360 and open the ISO and extract to external hdd like you would anyother ISO
4: ISO can be read from any ISO mounter
Michalss, done that, but it did not work too, but I already know where I was going wrong.
In JTAG console to record a game on the HDD, it creates a folder with the name of the game such game FABLE III

058682BA0A52DAE81710298F565596C04D.data

This is the folder of the game FABLE III but for the JTAG can identify the folder and run it generates an index file with the same name, and with a small size, eg.

058682BA0A52DAE81710298F565596C04D (44Kb)

I found that all games recorded on the HDD generates this file for identification, the difference is that this file is in JTAG along with the example folder.

058682BA0A52DAE81710298F565596C04D.data
058682BA0A52DAE81710298F565596C04D (44Kb)

Already in the original console that file is in the system, in a kind of library of games.

Now what I'll do is try to extract these files without damaging the console, after successfully do this, I'm pretty sure that any translation or MOD games can run on all consoles, unlocked or not.

Someone would assist in creating a script for the above file?
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-07-08T19:53:23+00:00
- Post Title: Questions about files xbox 360/XBLA

All files are signed on retail consoles. When you change these files the signature breaks and so will your mod.
