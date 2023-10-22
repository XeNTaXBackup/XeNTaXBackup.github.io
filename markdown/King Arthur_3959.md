## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-19T23:54:59+00:00
- Post Title: King Arthur

I guess that the demo of 2 gigabytes (what???) will not pass unobserved so I have decided to take a look at the PAK archives of this game because I was enough sure that now or later this thread would have been opened by someone else :)

*update* use QuickBMS 0.3.12
[http://aluigi.org/papers/bms/king_arthur.bms](http://aluigi.org/papers/bms/king_arthur.bms)
## Post #2
- Username: SCGame
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 13, 2009 8:41 am
- Post datetime: 2009-12-20T18:59:41+00:00
- Post Title: King Arthur

Great job! Those two scripts work very well.

But I think those two bms scripts work for all pak files except for UI\Files.PAK
I extracted the file from this pak file with king_arthur.bms, I get only one 300MB zip file.
The script zip.bms didn't work for it.

Would you like to try to extract the file from UI\Files.PAK, aluigi? 
Thank you.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-20T20:20:42+00:00
- Post Title: King Arthur

unfortunately UI\Files.pak doesn't contain files in crypted mode, that's the cause of the problems.
well seems that the only thing to do for this file would be handling it in the correct way but I can't help at the moment with the full reversing of the format.
maybe if I will add a getbits function in QuickBMS I could have a personal interest in continuing the job, but not now
## Post #4
- Username: SCGame
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 13, 2009 8:41 am
- Post datetime: 2009-12-20T23:12:04+00:00
- Post Title: King Arthur

That's OK. Thanks again for those two quickbms scripts
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-20T23:59:13+00:00
- Post Title: King Arthur

a small update.
I have implemented everything in my beta version of quickbms that I have finished just in this moment, so stay tuned tomorrow when I will release it and the udpated script for this game (format completely reversed)
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-21T17:18:23+00:00
- Post Title: King Arthur

as promised I have updated [the script](http://aluigi.org/papers/bms/king_arthur.bms) and quickbms to [version 0.3.12](http://aluigi.org/papers.htm#quickbms) for supporting the reading of the bits.

then now you no longer need zip.bms because the "unzipping" of the crypted file is performed in real time by the same script :)
## Post #7
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-09-11T12:55:10+00:00
- Post Title: King Arthur

I attach a sample for The Saxons Expansion, maybe the key is different?
[WarriorsFlail_rollover.dds - 0.01MB](http://www.zshare.net/download/80293003cd501327/)
[WarriorsFlail_rollover.7z](https://xentaxbackup.github.io/file/3427_WarriorsFlail_rollover.7z)
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-09-17T18:49:27+00:00
- Post Title: King Arthur

the key is still the same, the only difference is that this one is a single file and not an archive like the pack/zip files for which the script was created.

don't worry I have updated it :)
[http://aluigi.org/papers/bms/king_arthur.bms](http://aluigi.org/papers/bms/king_arthur.bms)
