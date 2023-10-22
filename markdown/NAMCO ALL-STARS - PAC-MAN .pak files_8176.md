## Post #1
- Username: gaming1233
- Rank: advanced
- Number of posts: 48
- Joined date: Mon Oct 11, 2010 4:36 am
- Post datetime: 2012-02-02T22:52:25+00:00
- Post Title: NAMCO ALL-STARS - PAC-MAN .pak files

This archive is used in the game NAMCO ALL-STARS - PAC-MAN. Could someone help me unpack it? Download: [http://www.mediafire.com/download.php?vxk3j5b39cqo6h5](http://www.mediafire.com/download.php?vxk3j5b39cqo6h5)
## Post #2
- Username: mrdo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 19, 2009 2:20 pm
- Post datetime: 2022-12-30T10:35:30+00:00
- Post Title: NAMCO ALL-STARS - PAC-MAN .pak files

I know I'm bumping a ten-year old thread... but I don't see that this one ever got resolved.

Just found this game... would like to be able to extract from the .pak archives here.

[https://drive.google.com/file/d/1x_S7K3 ... sp=sharing](https://drive.google.com/file/d/1x_S7K3NaadXQuKvqIjlCHbbpfyk6lj30/view?usp=sharing)
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-30T11:37:46+00:00
- Post Title: NAMCO ALL-STARS - PAC-MAN .pak files

Hm, I've checked your samples and index seems to be encrypted in all files except "launcher_pm.pak":
I think I would be able to figure out encryption method and file format, but I need some time.



screenshot000272(1).png (198.44 KiB) Viewed 57 times
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-01-01T19:26:24+00:00
- Post Title: NAMCO ALL-STARS - PAC-MAN .pak files

So I was able to do some research on Namco All-Stars Dig Dug, which has very similar encryption to this Pac-Man game.

File format looks like this [http://wiki.xentax.com/index.php/Namco_All-Stars_PAK](http://wiki.xentax.com/index.php/Namco_All-Stars_PAK)
This archive type uses some kind of subtract encryption.

Here is my Python tool for data extraction:
[https://github.com/bartlomiejduda/Tools ... PAK%20Tool](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools/Namco%20All-Stars/Namco%20All-Stars%20PAK%20Tool)
Usage is explained in the readme file on Github.

I've tested it on Dig Dug and it works fine, but it has some issues with other games. Apparently encryption method is not exactly the same for all games (or my tool just doesn't support all variants).


By the way, main Dig Dug executable can be packed with PECompact 2.98 packer. So to do some static analysis, it needs to be unpacked first (for example, with OllyDbg and some scripts and plugins).
