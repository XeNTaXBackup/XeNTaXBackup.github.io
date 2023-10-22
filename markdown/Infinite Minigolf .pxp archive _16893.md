## Post #1
- Username: ultima
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 08, 2009 12:37 pm
- Post datetime: 2017-08-20T22:41:54+00:00
- Post Title: Infinite Minigolf *.pxp archive ?

Hello,

is anyone can extract the files (and possibly repack) in pxp archives of Infinite Minigolf.

[https://mega.nz/#!t5pFGDwK!YHAscQXARH_B ... bv9WzVqgAg](https://mega.nz/#!t5pFGDwK!YHAscQXARH_B2l4HcUNPKY4jEdyTto6xgbv9WzVqgAg)

Thank you in advance.

(Sorry for my english> _ <)
## Post #2
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-08-25T11:49:49+00:00
- Post Title: Infinite Minigolf *.pxp archive ?

I checked the file. Header PX + ushort and two uints unknown. File compressed by LZSS LZS or similar because on x3d3b6e you can see warped text that gets terminated on section by 00s and some text is completed with previous buffer. My guess is LZSS

0xC is filelength (incl. header)
I don't see filenames, just content so it may be hashed

Some source is also scrapped (SVN paths)
