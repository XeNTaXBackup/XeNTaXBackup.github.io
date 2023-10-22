## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-28T02:23:42+00:00
- Post Title: [Request] Elsword

Textures: DDS-TGA
Mesh: Y-X (I think)
Unknown: LUA-TET



Y & X files have this in the header.



[Elsword 2D-3D Samples](http://www.mediafire.com/download.php?gy684ohw3kt3033)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-28T03:49:02+00:00
- Post Title: [Request] Elsword

Just binary directx file compressed using bzip.

I think the directx SDK comes with tools for opening that.
I've been wanting to write a decompressor but never got to it.

.Y files are regular directx text format.
## Post #3
- Username: illian
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Feb 05, 2012 8:36 pm
- Post datetime: 2013-06-24T10:59:29+00:00
- Post Title: [Request] Elsword

Do you have any tool to decompress files compressed with Bzip?
I've tried Bzip2, but seems to not work :/
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-24T14:28:18+00:00
- Post Title: [Request] Elsword

did you try
[viewtopic.php?f=21&t=9064](http://forum.xentax.com/viewtopic.php?f=21&t=9064)
## Post #5
- Username: illian
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Feb 05, 2012 8:36 pm
- Post datetime: 2013-06-24T19:55:16+00:00
- Post Title: [Request] Elsword

What is the proper header of an uncompressed .x?
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-24T20:42:28+00:00
- Post Title: [Request] Elsword

depends on the file format
most likely
xof 0303txt 0032
or 
xof 0303bin 0032
or in hex
78 6F 66 20 30 33 30 33 74 78 74 20 30 30 33 32
or
78 6F 66 20 30 33 30 33 62 69 6E 20 30 30 33 32

[http://paulbourke.net/dataformats/directx/](http://paulbourke.net/dataformats/directx/)
## Post #7
- Username: illian
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Feb 05, 2012 8:36 pm
- Post datetime: 2013-06-25T11:02:38+00:00
- Post Title: [Request] Elsword

It works!   

Thank you Chrrox
