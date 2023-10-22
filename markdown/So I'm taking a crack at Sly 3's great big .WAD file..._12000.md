## Post #1
- Username: Ryusui
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 02, 2014 1:43 pm
- Post datetime: 2014-09-24T08:49:12+00:00
- Post Title: So I'm taking a crack at Sly 3's great big .WAD file...

I have PS2dis, the latest dev version of PCSX2 with the brand-new debugger, prior experience deciphering compression and archive formats...and a woeful lack of PS2 hardware knowledge.

Having determined little from my probings into a small sample of the colossal 3GB SLY3.WAD, I'm thinking my best option is, naturally, to catch the game in the act of loading data from it and work out what it does to decode or decompress that data. I've found a great guide to PS2 ASM which has helped bridge the gap between the somewhat foreign mnemonics and my own ASM experience. The problem is, I've yet to figure out how to catch the system in the act of loading data from a specific file. There are no labels that I can find pointing to the titanic WAD, so my only hope (as I've done on DS) is to figure out how PS2 games load files from media and figure out where the data lands in memory.

Could anyone with more experience on the subject point me in the right direction?
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-09-24T15:13:45+00:00
- Post Title: So I'm taking a crack at Sly 3's great big .WAD file...

I wrote an unpacker for the HD Version of Sly (not sure which game). Doubt it's the same format though.
## Post #3
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-04-03T11:01:39+00:00
- Post Title: So I'm taking a crack at Sly 3's great big .WAD file...

> Reply from Ryusui
>
> I have PS2dis, the latest dev version of PCSX2 with the brand-new debugger....
Deleted. PM you instead.
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-04-18T18:36:36+00:00
- Post Title: So I'm taking a crack at Sly 3's great big .WAD file...

Aluigi wrote a BMS script not too long ago that handles all of the .WAD files from each of the three games on both PS2 and even the HD Collection games.

The thread about it can be found [here](http://zenhax.com/viewtopic.php?p=3158)

The BMS script can be found [here](http://aluigi.altervista.org/papers/bms/others/sly_wal.bms)

If your goal is to understand the format of the archive, this should help
