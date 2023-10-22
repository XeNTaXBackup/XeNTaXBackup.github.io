## Post #1
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2013-09-30T00:06:16+00:00
- Post Title: [Sen no kisek] Change python code to quickbms..?

Does anyone can make a quickbms code instead of python code..?
I want to repack *.bin files to *.dat files using quickbms repack option.
*The python code only uncompress *.dat files to *.bin files.

*code was deleted.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-09-30T07:34:37+00:00
- Post Title: [Sen no kisek] Change python code to quickbms..?

it looks like a RLE algorithm.
Quickbms contains the only recompression algorithms most used in games like zlib, lzo, lzma and so on, small ones are not covered.
## Post #3
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2013-09-30T09:27:08+00:00
- Post Title: [Sen no kisek] Change python code to quickbms..?

> Reply from aluigi
>
> it looks like a RLE algorithm.
Quickbms contains the only recompression algorithms most used in games like zlib, lzo, lzma and so on, small ones are not covered.

Oh..my god. Then..There's no way.. I can't make a recompression python code.   
And it is impossible someone will make it..
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-09-30T10:43:36+00:00
- Post Title: [Sen no kisek] Change python code to quickbms..?

You don't need to recompress the files. The game will read uncompressed files.
## Post #5
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2013-09-30T11:12:11+00:00
- Post Title: [Sen no kisek] Change python code to quickbms..?

> Reply from chrrox
>
> You don't need to recompress the files. The game will read uncompressed files.

Hmm.. It is PS3 game. How does it work without recompressed files..?
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-09-30T19:35:49+00:00
- Post Title: [Sen no kisek] Change python code to quickbms..?

Only the fonts and game text was compressed you can re create the archives without using compression like all the other archives the game uses and it should read fine.
