## Post #1
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-11-11T14:25:04+00:00
- Post Title: Extract all CTPK-Files from an Arc-file (3DS)

Hey Guys,

I want to extract all .ctpk-files from a .arc (ARCV Header, not supported by Every File Explorer) to edit them.
I've uploaded a archive which contains one of this .arc-files.
[http://www.xup.in/dl,18666304/system.7z/](http://www.xup.in/dl,18666304/system.7z/)

The CTPK-FIles inside of this archive are uncompressed and every CTPK-File has his own header which looks like this:

> CTPK....€.... ..P...X...........D.... ..........€.@.........ouÓQ. ..ascii.tga...Ã¾U.....ÿ.......................................
(header size = 80bytes)
The rest of this file is a image in RGBA4-Format.

I just want to extract the files with a BMS-Script (and probably reinsert them with it).

Could someone help me out with a BMS-Script which extracts this files for me?
## Post #2
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-11-12T10:23:24+00:00
- Post Title: Extract all CTPK-Files from an Arc-file (3DS)

//Push
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-13T16:43:55+00:00
- Post Title: Extract all CTPK-Files from an Arc-file (3DS)

[http://aluigi.org/bms/3ds_arcv.bms](http://aluigi.org/bms/3ds_arcv.bms)
