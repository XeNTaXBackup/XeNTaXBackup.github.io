## Post #1
- Username: zander1995
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 02, 2011 5:55 am
- Post datetime: 2016-10-08T02:33:54+00:00
- Post Title: Vita (AIR) Prototype (company) .PAK files?

I've been messing around with a recent PSVita game from [Prototype](https://en.wikipedia.org/wiki/Prototype_%28company%29) but despite my best efforts, I've been unable to figure out how to unpack their .pak archives.

Each .PAK file comes with an included .TBL file, which I'm pretty sure includes all the needed information about the file sizes and locations in the relevant .PAK file. Problem is, I'm not able to figure out how to actually extract the .PAK files (let alone attempt to repack them.)

Here's the headers for one pair of files.

psvsys.tbl


psvsys.pkg


Edit:
Download for two pairs of files.

[http://www.mediafire.com/file/7cu8t12zr ... G00940.rar](http://www.mediafire.com/file/7cu8t12zrsu7ej1/PCSG00940.rar)

Includes:
1. psvscr.tbl/pak (Game scripts)
2. psvsys.tbl/pak (System files)

 PCSG00940
## Post #2
- Username: RikuKH3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jul 26, 2012 7:37 am
- Post datetime: 2017-10-21T04:22:58+00:00
- Post Title: Vita (AIR) Prototype (company) .PAK files?

I made unpacker for this type of archives:
[https://github.com/RikuKH3/prot_tblpak/releases](https://github.com/RikuKH3/prot_tblpak/releases)
Tested with a few Vita, PS3 and Android games, works fine.
