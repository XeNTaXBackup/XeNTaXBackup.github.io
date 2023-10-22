## Post #1
- Username: Nukem
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 28, 2006 9:00 pm
- Post datetime: 2009-02-26T23:11:32+00:00
- Post Title: Quake Live     *.pk3 archive files

As  Quake Live  is in a open beta for some days now, I created an account and tried it.
After waiting a (felt) bazzillion of minutes I could try it. (I left my laptop running in the queue to get from #12,547-something down to the fun - maybe half an hour... )
Unfortunately, after pwnding Crash away in nothing for 12 times, the "self-adjusting A.I."  tuned her so godlike she won 15-12 and then QL told me I HAVE to make the first match in order to proceed (for skill-checking of course). 
(I didn't know that I also have to WIN that one?!?)
Unfortunately, again, after retrying that match, when I was about to win (YES!) shortly before the time-out the QL-plugin (and with it Firefox) crashed... 
The QL homepage shortly before said my connection was broken - WTF?!

But to make a long story short: I was wondering if I could play the training map in the old-skool Q3A game, and when I checked the Quake Live stuff (which was downloaded while playing the skill-checking match) I found a bunch of *.PK3 files (>250 MB together).

Unfortunately, these are not the *.PK3- aka *.ZIP-files that Quake 3 Arena had.

Maybe somebody already examined them and has some infos about them??
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-02-26T23:43:55+00:00
- Post Title: Quake Live     *.pk3 archive files

the pk3 files of quakelive are simply xored with a big fixed sequence of bytes:
[http://aluigi.org/papers.htm#q3](http://aluigi.org/papers.htm#q3)
## Post #3
- Username: dimwalker
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 18, 2009 6:06 am
- Post datetime: 2009-03-25T09:19:58+00:00
- Post Title: Quake Live     *.pk3 archive files

Thanks a lot. Nice tool, but latest .pk3 create archives with dummy file, so I guess they had changed something in encryption method.
Is there newer version or any similar program?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-03-25T21:03:11+00:00
- Post Title: Quake Live     *.pk3 archive files

the key and the encryption is still the same (if you can open/extract/verify/test the pk3/zip archives means that it's correct).

the dummy files are not part of the encryption or related to them, they are just normal files inside the pk3/zip archives
## Post #5
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2014-09-20T13:53:23+00:00
- Post Title: Quake Live     *.pk3 archive files

.pak archive? (web.pak, inspector.pak.)

[](http://radikal.ru/fp/d5e6263594f349e2b47ee82efe781b28)
