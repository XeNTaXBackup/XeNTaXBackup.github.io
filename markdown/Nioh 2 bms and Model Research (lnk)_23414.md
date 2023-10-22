## Post #1
- Username: Trophi Hunter
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 09, 2015 2:50 pm
- Post datetime: 2021-02-07T23:40:25+00:00
- Post Title: Nioh 2 bms and Model Research (lnk)

So I have been able to use the nioh 1 bms script to extract the .lnk archives, however there are at least 2 that wont extract, archive_17, is the largest at 32GB and gives a size error.

offset           filesize   filename
--------------------------------------
  0000000000013000 2352       0000000000000000.dat

Error: the compressed zlib/deflate input is wrong or incomplete (-3)
Info:  algorithm   1
       offset      0000000000013000
       input size  0x0000000000003c2f 15407
       output size 0x0000000000000930 2352
       result      0xffffffffffffffff -1

Error: the uncompressed data (-1) is bigger than the allocated buffer (2352)
       It usually means that data is not compressed or uses another algorithm

Last script line before the error or that produced the error:
  17  clog "" OFFSET ZSIZE SIZE

any insight on this would be appreciated. I am trying to find the character creation assets, hair to be specific, Ninja ripper does work but exporting that way is even more tedious.
## Post #2
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2021-07-03T15:25:32+00:00
- Post Title: Nioh 2 bms and Model Research (lnk)

HI! Would you might sharing how to use ninja ripper?? As i can't run it with nioh 2 at all.
