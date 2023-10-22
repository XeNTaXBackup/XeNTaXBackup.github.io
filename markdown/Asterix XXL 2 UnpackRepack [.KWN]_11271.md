## Post #1
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2014-03-01T18:18:43+00:00
- Post Title: Asterix XXL 2 Unpack/Repack [.KWN]

Hi,

Is there a way of unpacking/repacking these files from Asterix XXL 2? I'm interested in translating this game.

Here's the samples: [https://drive.google.com/file/d/0B1GkDg ... sp=sharing](https://drive.google.com/file/d/0B1GkDgp3kpRpQ1oxa3NndXVOdGs/edit?usp=sharing)

Thank you.
## Post #2
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2014-03-07T12:36:54+00:00
- Post Title: Asterix XXL 2 Unpack/Repack [.KWN]

Anyone?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-03-07T17:56:00+00:00
- Post Title: Asterix XXL 2 Unpack/Repack [.KWN]

00GLOCK.KWN: you'll have to understand the structure of the unicode table at the beginning.
Then translate it.

At 0x000C there seems to be the end address of the table: 0x12AC2

Has to be adjusted according to the length of your translated table.

Don't know whether this will be sufficient - you'll have to try it out.

After the table there's picture data:
[](http://www.pic-upload.de/view-22480300/00Glock_KWN.jpg.html)

At file end unknown data.
