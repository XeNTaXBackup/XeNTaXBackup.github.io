## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-11-22T15:52:32+00:00
- Post Title: [PS3] PlayStation All-Stars Battle Royale (PSARC)

Anyone seen PSARC files like these before... valid header and TOC, but zlib chunks start with either 0x0001 or 0x0002 usually. Tried using latest leaked psarc.exe but no luck. Also tried my own zlib extractor and messed with adding common zlib signatures but no luck.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-11-22T17:54:20+00:00
- Post Title: [PS3] PlayStation All-Stars Battle Royale (PSARC)

if you look in the elf file they mention sdat encryption. I think these are sdat encrypted psarc files. Also i notice there is a sub version of 4 in these files I am thinking it stands for sdat encryption v4.
I was planning on dumping the games ram to get some models and compare some things. Even if its not sdat encryption its got to be some kind of encryption its mentioned all over the executable.
## Post #3
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2012-11-22T22:58:45+00:00
- Post Title: [PS3] PlayStation All-Stars Battle Royale (PSARC)

How does one go about dumping RAM from the PS3, anyway? I'll want to know once my currently-dead PS3's up and running again.
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-11-22T23:23:40+00:00
- Post Title: [PS3] PlayStation All-Stars Battle Royale (PSARC)

fuuuuuuuuu lol. i figured encrypted streams as well, but with consistent 0x0001 or 0x0002 i thought it might be even something simpler than sdat. good luck with the core dump. you using multiman to do the dump?
## Post #5
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-23T00:56:50+00:00
- Post Title: [PS3] PlayStation All-Stars Battle Royale (PSARC)

It would be great even.

Thank you to all who already are seeing it.
## Post #6
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-11-24T00:44:25+00:00
- Post Title: [PS3] PlayStation All-Stars Battle Royale (PSARC)

Chroxx in here, a good signal...
## Post #7
- Username: soneek
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Oct 20, 2011 5:43 am
- Post datetime: 2013-01-04T09:44:49+00:00
- Post Title: [PS3] PlayStation All-Stars Battle Royale (PSARC)

Sorry to bump this, but has there been any luck in extracting this version of PSARC archives?
## Post #8
- Username: dragbody
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-07T12:51:08+00:00
- Post Title: [PS3] PlayStation All-Stars Battle Royale (PSARC)

I hope to get around to dumping the ram of this game to examine what's happening.
There is a guide here for people with custom firmware to try if you want to get a jump start on this.
[http://www.nextgenupdate.com/forums/pla ... dding.html](http://www.nextgenupdate.com/forums/playstation-3-mods-cheats/619381-real-time-game-memory-modding.html)
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-24T03:36:27+00:00
- Post Title: [PS3] PlayStation All-Stars Battle Royale (PSARC)

I finally got around to setting up my console as a debug ill let people know if i find anything.
I am fairly sure the files are encrypted there is a function named this in the elf.
$#@!__DecryptPsarcs__!@#$decrypt
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-01-24T03:42:56+00:00
- Post Title: [PS3] PlayStation All-Stars Battle Royale (PSARC)

awesome ha ha ha ha ha
## Post #11
- Username: KuchiBoy
- Rank: Banned
- Number of posts: 21
- Joined date: Wed May 23, 2012 3:35 am
- Post datetime: 2013-03-08T02:53:32+00:00
- Post Title: [PS3] PlayStation All-Stars Battle Royale (PSARC)

sorry to bump but is there any progress on this?
## Post #12
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2013-03-14T22:04:32+00:00
- Post Title: [PS3] PlayStation All-Stars Battle Royale (PSARC)

Did you ever get anywhere with the $#@!__DecryptPsarcs__!@#$decrypt? Surely you can't just stop after getting this close.
## Post #13
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-26T22:45:08+00:00
- Post Title: [PS3] PlayStation All-Stars Battle Royale (PSARC)

> Reply from chrrox
>
> I finally got around to setting up my console as a debug ill let people know if i find anything.
I am fairly sure the files are encrypted there is a function named this in the elf.
$#@!__DecryptPsarcs__!@#$decrypt
Well i found Total Commander plugin for work with PS3 PSARC files. Here small part from readme 

```

+ Plugin crashing on opening PSARC with unknown compression algorithm fixed.
  E.g. in "PlayStation All-Stars Battle Royale" PSARCs.
```


I guess [it's help you](http://www.totalcmd.net/plugring/PSARC.html)
## Post #14
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-11-30T03:25:16+00:00
- Post Title: [PS3] PlayStation All-Stars Battle Royale (PSARC)

I tried using Total Commander with the PSARC plugin but I get the following error:

```
Unpack() - inflate() is wrong
```


Any ideas?
## Post #15
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-30T03:55:45+00:00
- Post Title: [PS3] PlayStation All-Stars Battle Royale (PSARC)

Its encrypted wont eve open with this plugin.
## Post #16
- Username: You'reAnAllStar
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 04, 2016 5:55 am
- Post datetime: 2017-10-17T21:45:24+00:00
- Post Title: Re: [PS3] PlayStation All-Stars Battle Royale (PSARC)

So has no one looked into this over the past 4 years? I know the game wasn't super popular but it's weird that this ended here
