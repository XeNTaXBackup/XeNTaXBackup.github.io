## Post #1
- Username: notless
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 02, 2021 9:25 pm
- Post datetime: 2021-05-10T10:49:00+00:00
- Post Title: Majesty - TILE and SPLT files

I've extracted what looks like run-length encoded image format with indexed colours and associated palette from the maindata.cam of Majesty.
I found an old tool called MajestyLibrary which let me extract these as bitmaps, but I can't figure out how it works.

First 3 are my attempts, 4th is what it should look like.


The attached zip includes the image format "tile1", the palette "splt1", and the bmp I was able to extract with MajestyLibrary.

The splt file contains some unknown data for the first 8 bytes and then a repeating sequence of 3 bytes of RGB and 1 zero byte 256 times. The index for each colour is as they appear in this file.

The tile files usually start with 03 00, then 2 bytes for the height, and 2 bytes for the width.
In this file there are then 264 bytes until the image data, the size of this block varies for larger images.
I can get a good result by treating every 0x80 as a row break and treating every other byte as an index into the palette, but I don't think this is the actual format.

The actual format appears to be built using 4-byte chunks, the first 5 bytes of this image are 1E 00 01 80 A7. 1E looks to be the starting column/x-coordinate, the 00 01 seems to be an input to 80 indicating that 1 palette-index byte is to follow, in this case, A7.
This 4-byte structure and following palette-indexes can be seen multiple times in the file, but this doesn't get a perfect result as it appears there are other 4-byte structures that I can't figure out.

Here's the start of tile1 with the first 5 bytes highlighted.

[majesty-data.zip](https://xentaxbackup.github.io/file/20097_majesty-data.zip)
## Post #2
- Username: notless
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-10T18:39:31+00:00
- Post Title: Majesty - TILE and SPLT files

I know it may be a long shot, but did you try contact original author of the MajestyLibrary tool?
It seems that his website is still online [https://www.oocities.org/the_rancid/dl-games.htm](https://www.oocities.org/the_rancid/dl-games.htm)
and you can find some contact info on the  site and in the readme file.
He may share some source code if you ask him.


But if you already contacted him and you got no response at all (which is possible after 20 years ;p),
you could try to reverse engineer this app with debugger.
Here are some tutorials for that [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
## Post #3
- Username: notless
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 02, 2021 9:25 pm
- Post datetime: 2022-02-23T09:33:04+00:00
- Post Title: Majesty - TILE and SPLT files

I was able to get in contact with TheRancid and he actually uploaded all his VB6 code to github.
[https://github.com/TheRancid/MajestyLibrary](https://github.com/TheRancid/MajestyLibrary)

His graphics code helped me solve my problems and finish off my Python library.
[https://github.com/timmot/majesty](https://github.com/timmot/majesty)

Thank you for the ideas!
