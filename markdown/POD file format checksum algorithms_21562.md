## Post #1
- Username: jopadan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 04, 2020 1:23 am
- Post datetime: 2020-01-03T18:16:40+00:00
- Post Title: POD file format checksum algorithms

Browsing all the code of the POD file format tools I didn't find any checksum algorithm support or information.

The checksum algorithm used in POD2 files is CRC-CCITT32 with seed 0xFFFFFFFF


A Collection of 32-bit CRC Tables and Algorithms [http://www.mrob.com/pub/comp/crc-all.html](http://www.mrob.com/pub/comp/crc-all.html)
which is based on 
macutils [http://github.com/dgilman/macutils](http://github.com/dgilman/macutils)
and now implemented in
Libcrc [http://github.com/jopadan/libcrc](http://github.com/jopadan/libcrc)

List of known POD format supporting programs without the checksum algorithm

QuickBMS [https://aluigi.altervista.org/quickbms.htm](https://aluigi.altervista.org/quickbms.htm)
podextract [https://github.com/ghoost82/podextract](https://github.com/ghoost82/podextract)
Dragon UnPACKer [https://github.com/elbereth/DragonUnPACKer](https://github.com/elbereth/DragonUnPACKer)
Game Extractor [http://www.github.com/wattostudios/GameExtractor](http://www.github.com/wattostudios/GameExtractor)
Terminal Recall [https://github.com/jtrfp/jtrfp](https://github.com/jtrfp/jtrfp)
Ghostbusters Unpack [http://svn.gib.me/public/ghostbusters/trunk](http://svn.gib.me/public/ghostbusters/trunk)
BloodRayne Tools [http://forum.xentax.com/blog/wp-content ... 7%CC%9A%D8](http://forum.xentax.com/blog/wp-content/plugins/download-protect/downloader.php?d=%93%DB%D3%CE%D0U%E8%97ko%9F%B4km%9A%A6%93%90%CF%95%E0%C2%9C%A7%DAs%9D%A6%D6%E8%D1%8F%E3%8B%E1%D5%94%B1%95%A7%A6%A4%93%E3%D9%C3%D7%8F%D6%C0%9B%AD%D4%B0f%99%D0%E2%CB%90%E2%96%A0%C4%A2%A7%DB%A9%A5%AB%93%E8%D4%CD%DA%87%D7%D4b%A9%D6%A8%AB%A6%D3%DF%D7%8F%E5%8F%E3&v=%D4%E5%CD%D7%CC%9A%D8)
GOBREAD [http://forum.xentax.com/blog/wp-content ... 7%CC%9A%D8](http://forum.xentax.com/blog/wp-content/plugins/download-protect/downloader.php?d=%93%DB%D3%CE%D0U%E8%97ko%9F%B4km%9A%A6%93%90%CF%95%E0%C2%9C%A7%DAs%9D%A6%D6%E8%D1%8F%E3%8B%E1%D5%94%B1%95%A7%A6%A4%93%E3%D9%C3%D7%8F%D6%C0%9B%AD%D4%B0f%99%D0%E2%CB%90%E2%96%A0%C4%A2%A7%DB%A9%A5%AB%93%E8%D4%CD%DA%87%D7%D4b%A0%D6%A6%A9%9C%C5%D7%92%DB%D4%96&v=%D4%E5%CD%D7%CC%9A%D8)
Nocturne Editor [https://www.moddb.com/downloads/nocturne-editor](https://www.moddb.com/downloads/nocturne-editor)

I am currently adding POD file format support to:
libpodfmt [https://github.com/jopadan/libpodfmt](https://github.com/jopadan/libpodfmt)
podorgana [https://github.com/jopadan/podorgana](https://github.com/jopadan/podorgana)
pup [https://github.com/jopadan/pup](https://github.com/jopadan/pup)
physfs [https://github.com/jopadan/physfs](https://github.com/jopadan/physfs)


=========================
libpodfmt crc-ccitt32 works?
=========================
entry : file/single
=========================
EPD   : no/no
POD2 : yes/yes
POD3 : no/yes
POD4 : no/yes
POD5 : no/yes
POD6 : no/yes
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-01-03T19:35:48+00:00
- Post Title: POD file format checksum algorithms

I think it's something of the standard CRC, FNV algorithms
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-01-04T12:33:05+00:00
- Post Title: POD file format checksum algorithms

What game are you exploring?
