## Post #1
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-11-05T17:23:49+00:00
- Post Title: Conflict/The Great Escape .sch files

[https://drive.google.com/file/d/1U7wqJe ... sp=sharing](https://drive.google.com/file/d/1U7wqJeVUnmPdrITKyXh3nF2L-bto-WPk/view?usp=sharing)

Any help will be appreciated.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-06T20:32:20+00:00
- Post Title: Conflict/The Great Escape .sch files

It seems that SCH file may be already partially (or fully?) supported by vgmstream.
I tried to open it with foobar, but it failed to load.
[https://github.com/vgmstream/vgmstream/ ... meta/psf.c](https://github.com/vgmstream/vgmstream/blob/master/src/meta/psf.c)
## Post #3
- Username: Edness
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 11, 2018 7:26 pm
- Post datetime: 2021-11-08T23:43:59+00:00
- Post Title: Conflict/The Great Escape .sch files

While I already answered with this on the Discord server, I'll post here just in case as well.  The problem here seems to just be the presence of IMUS and PFST sections.  I made a QuickBMS script to strip those and only keep BANK/PFSM sections, which then works just fine with vgmstream.

[https://raw.githubusercontent.com/Ednes ... -strip.bms](https://raw.githubusercontent.com/EdnessP/scripts/main/other/sch-imus-strip.bms)
