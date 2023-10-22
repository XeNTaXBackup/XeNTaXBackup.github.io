## Post #1
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2009-11-22T09:34:45+00:00
- Post Title: Inquisitor game .dat archives [DRPK]

Hi
I would like to extract files from .dat archives in Inquisitor game. [http://games.cinemax.cz/inquisitor](http://games.cinemax.cz/inquisitor)

I tried to unpack it by myself, but I think there is some kind of encryption...
Magic is 'DRPK' som I suppose that it's a kind of ZIP archive...

[](http://img243.imageshack.us/i/inquisitor.png/)

I uploaded a few files and .exe here: [http://www.filefront.com/14960813/Game.zip/](http://www.filefront.com/14960813/Game.zip/) ~ 18MB

Anyway I tried to dissasemble it with IDA disassembler but no massive success

```
Game at start looks for *.dat files in current directory - but dunno whether it decrypt them immediately or load to memory
Then a 'intro' is played - probably file 'movie00.wmv' [I found this in strings of exe] <- this file is in archives too, so I think it is decrypted before loading...

My idea is to catch 'decryption process' and find out pre proper operation [XOR, OR, AND ...] and parameters

```


Please help with these... thx
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-22T11:47:30+00:00
- Post Title: Inquisitor game .dat archives [DRPK]

[http://aluigi.org/papers/bms/inquisitor.bms](http://aluigi.org/papers/bms/inquisitor.bms)
remember to use quickbms 0.3.9 because I implemented a easier way to handle the chunks of compressed data compressed with slf_block
## Post #3
- Username: DuchessOfKvetch
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 06, 2013 12:56 am
- Post datetime: 2013-09-06T21:31:30+00:00
- Post Title: Inquisitor game .dat archives [DRPK]

Sorry for the thread necro, but there's been no mention of this game in a few years, and now a newer version is out in English. I'll open a new thread if I can get past certain showstoppers.

So, does reimporting work with this BMS script? I am using QuickBMS 5.2.4a, and getting the error "unsupported compression 118 in reimport mode". Not sure if this is symptomatic of an unreported bug, or if the bms script (which looks like a small one) lacks the necessary details.

As it is, the extracted archives won't work on their own.
