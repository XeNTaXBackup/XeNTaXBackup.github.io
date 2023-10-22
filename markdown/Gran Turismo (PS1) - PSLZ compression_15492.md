## Post #1
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-11-14T00:20:10+00:00
- Post Title: Gran Turismo (PS1) - PSLZ compression

Well, I had to call the compression algorithm "PSLZ" because it was hinted at the executable files.

Here is a sample if anyone wants to crack it.
[CARINF.rar](https://xentaxbackup.github.io/file/11914_CARINF.rar)
## Post #2
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-03-11T14:28:43+00:00
- Post Title: Gran Turismo (PS1) - PSLZ compression

At first sight it looked like LZSS and indeed it decompressed succesfully but the file afterward is complete mess
Take a look at: 0x7044
If you delete every 0x09th byte from here you can get nice text:
TOYOTA\0 0x06 NISSAN\0
MITSUBISHI\0 0x05HONDA

after that there should be MAZDA but it's only MAZ (DA is missing, it's get few bytes earlier) [also the text length byte is still there 0x05, but the characters are missing]. This is typical for LZS-like compressions, so it's some variation of LZS [not LZSS as said above]
## Post #3
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2017-04-15T01:28:37+00:00
- Post Title: Gran Turismo (PS1) - PSLZ compression

> Reply from MaKiPL
>
> This is typical for LZS-like compressions, so it's some variation of LZS [not LZSS as said above]Huh. I`ll guess I need to look exactly which variation of LZS was used so I can get the result. Thanks for the hint!

EDIT: So I guess Gran Turismo has its own LZS compression variant. The only hint that these files use such kind of compression are in the executables of the game itself(GTEND.EXE, GTMAIN.EXE, GTMENU.EXE, GTOS.EXE and the executable whose filename looks like a serial number of a regional version of the game). Should I post these executables in question?
