## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-03-04T00:54:56+00:00
- Post Title: Real time memory dumper.

Does anyone know of a working program that can dump memory real time to from a game or other running process?
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-04T15:16:09+00:00
- Post Title: Real time memory dumper.

procdump from sysinternals.
with the -ma option dumps the whole memory in MDMP format and has also some interesting other options.
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-04T22:20:33+00:00
- Post Title: Real time memory dumper.

OllyDBG is not satisfied? ALT+M , select region what you need , right click > Dump , in new window right click > Backup -> Save data to file
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-03-05T18:41:14+00:00
- Post Title: Real time memory dumper.

Im new  ollydbg. So do i open the exe with the program and then run the game?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-03-06T10:20:38+00:00
- Post Title: Real time memory dumper.

> Reply from OrangeC
>
> Im new  ollydbg. So do i open the exe with the program and then run the game?Depends on the game. For games which run code for copy protection at startup this may not work.

But you can start your game as usual then start olly, File, Attach (to your game process).

After this continue as Ekey wrote.
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-03-16T20:33:50+00:00
- Post Title: Real time memory dumper.

Procdump catches only 500MB of memory. I monitored the process of a game for like 20minutes and when exited it dumped like only 500MB and some info was missing. Anyway to increase the size limit?
