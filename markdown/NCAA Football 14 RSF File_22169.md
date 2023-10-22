## Post #1
- Username: LtCheeseburger
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 19, 2020 1:30 am
- Post datetime: 2020-05-18T17:41:43+00:00
- Post Title: NCAA Football 14 RSF File

While looking through game files from NCAA FB 14 AST Files, ive stumbled across multiple RSF files which may contain geometry, shaders, and a ton of other stuff for 3D models within the game.I cant figure out how to extract files from said RSF  I've provided one of the files in question, any help would be appreciated!
[NCAAFB14RSF.zip](https://xentaxbackup.github.io/file/18167_NCAAFB14RSF.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-18T18:57:09+00:00
- Post Title: NCAA Football 14 RSF File

Using hex2obj (view link in my sig), first submesh only:
.



LIFESIZE_CHAMPSUNBELT.png (65.92 KiB) Viewed 173 times
## Post #3
- Username: LtCheeseburger
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 19, 2020 1:30 am
- Post datetime: 2020-05-19T02:22:25+00:00
- Post Title: NCAA Football 14 RSF File

THANK YOU!
## Post #4
- Username: LtCheeseburger
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 19, 2020 1:30 am
- Post datetime: 2020-05-20T17:37:37+00:00
- Post Title: NCAA Football 14 RSF File

> Reply from shakotay2 ↑Tue May 19, 2020 2:57 am at Tue May 19, 2020 2:57 am
>
> 
Using hex2obj (view link in my sig), first submesh only:
.
LIFESIZE_CHAMPSUNBELT.png
How did you find the face indices, vertex block, get vertices? I've looked at countless videos and read the tutorials on here countless times and i havent gotten anywhere.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-20T17:54:47+00:00
- Post Title: NCAA Football 14 RSF File

"countless"? Really? I can't believe it since this is a very simple mesh format (except for the uvs). Once you've found the "scrambled alphabet" (face indices) there's no great hurdle any more to get the first submesh. (May be a little bit more difficult in case it's the first 3D format you deal with. Detecting Big Endian as used data format for console games should not be a surprise, though.)
## Post #6
- Username: LtCheeseburger
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 19, 2020 1:30 am
- Post datetime: 2020-05-21T04:21:11+00:00
- Post Title: NCAA Football 14 RSF File

> Reply from shakotay2 ↑Thu May 21, 2020 1:54 am at Thu May 21, 2020 1:54 am
>
> 
"countless"? Really? I can't believe it since this is a very simple mesh format (except for the uvs). Once you've found the "scrambled alphabet" (face indices) there's no great hurdle any more to get the first submesh. (May be a little bit more difficult in case it's the first 3D format you deal with. Detecting Big Endian as used data format for console games should not be a surprise, though.)

Im sort of new to this just trying to learn the ropes.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-21T17:49:06+00:00
- Post Title: NCAA Football 14 RSF File

This format (except for the uvs, as I wrote) is very good to learn from, imho.

Simple strings lead the way, "STRM", "INDX" :

Or calculate addr of next submesh:
first submesh start: 0x1d4
205x40=8200 (dec.)= 0x2008, size of vertex block
0x1d4+0x2008= 0x21dc -> "STRM"
You'll need to add 0x15 (don't ask me why, matter of the format  ) to get the next submesh (SM) address:

    0x1BF    +0x15 -> 0x1d4, SM1 
    0x21DC    -> 0x21F1, SM2
    0x4221    -> 0x4236, SM3
Further "STRM" strings at:
    0x4F56, 0x91AB,  0xB6A0, 0xB755, 0xC76E, 0xD79B, 0xDE40, 0xFF25, 0x111AA

-------------------------
face index (FI) blocks:
0x11224 +756x2 (dec.)= 0x1180C ->  "INDX", add 0x11 to get the start address of the next FI block

+0x11 = 0x1181d, end of FI block:  0x11cd9

Copy the following 6 lines into an empty txt file, rename it to whatever.H2O, load mesh then H2O file into hex2obj:

0x1181D 606
Vb1
40 24
0x21F1 206
120100
0x0 255
.



LIFESIZE_CHAMPSUNBELT_SM2.png (59.29 KiB) Viewed 121 times
