## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-19T03:05:45+00:00
- Post Title: Total size of dds

I can't seem to figure this out.

I have a plain dds file in front of me, and I want to figure out how many bytes in total the file takes up.
I went to microsoft site to get information about DDS and found the size of the header, but can we calculate the size of the data from the header alone?
## Post #2
- Username: JU57FL1P
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 29, 2011 6:16 pm
- Post datetime: 2011-08-20T18:42:01+00:00
- Post Title: Total size of dds

maybe this will help:
[WTV.rar](https://xentaxbackup.github.io/file/4647_WTV.rar)
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2011-08-20T20:58:34+00:00
- Post Title: Total size of dds

Basically DXT1 has compression of 1:8, DXT3 & DXT5 are both 1:4
so for an 64 X 64 image, uncompressed size will be 64X64X4(RGBA) = 16384 (0x4000)
for DXT1 => 0x800, DXT3/DXT5 => 0x1000

for each mipmap, it will be half the size of the previous level
so, 1st mipmap of the above image is 32X32.  DXT1 =>0x200 DXT3/DXT5 => 0x400
2nd mipmap will be 16X16, 3rd mipmap will be 8X8...
