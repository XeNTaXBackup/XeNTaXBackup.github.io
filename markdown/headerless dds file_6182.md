## Post #1
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2011-03-06T16:14:43+00:00
- Post Title: headerless dds file

I need help figuring out the dimensions of this image file. If the file size is 0x20000 bytes, and theres 4 bytes in one pixel, shouldn't you get the dimensions by doing sqrt(0x20000 / 4)?

I have sort of working (the colors seem to be correct).
[image.png](https://xentaxbackup.github.io/file/4017_image.png)
## Post #2
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-03-07T08:11:48+00:00
- Post Title: headerless dds file

Without the file, we can't help.
## Post #3
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-03-20T01:12:23+00:00
- Post Title: headerless dds file

If it is DTX1 then there are 4 bits per pixel, meaning that the size should technically be:

Assuming height and width are the same.
height = sqrt(0x20000 / (4 / 8 ))
height = sqrt(262144)
height = 512
therefor width is 512


tl;dr the resolution should be 512x512
