## Post #1
- Username: toadbirb
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 04, 2022 1:14 pm
- Post datetime: 2023-04-19T23:10:11+00:00
- Post Title: Netease - Identity V | Uncompressed Data Error

I'm facing an issue with a Netease game titled Identity V where I'm now unable to export assets for some of the games NPKs due to a "uncompressed data" and "compressed zlib/deflate input is wrong or incomplete" error (example included below of the error) when trying to use QuickBMS.

If anyone has any insight about how I can fix this issue id very much appreciate it!

```
Info:  algorithm   1
       offset      00000000
       input size  0x0000025a 602
       output size 0x00000e2b 3627
       result      0xffffffff -1

Error: uncompressed data (-1) bigger than allocated buffer (3627)
       It usually means that data is not compressed or uses another algorithm

Last script line before the error or that produced the error:
  207 clog NAME OFFSET ZSIZE SIZE FILENUM

- OFFSET       0x00000000
- ZSIZE        0x0000025a
- SIZE         0x00000e2b
  coverage file 0     0%   654        4103844    . offset 003d6e94
  coverage file -1  100%   602        602        . offset 0000025a
```

TDLR:
Game: Identity V
Issue: uncompressed data error / compressed zlib/deflate input is wrong or incomplete
Example NPKs: [https://www.dropbox.com/s/dxto2s1wnm8sp ... s.rar?dl=0](https://www.dropbox.com/s/dxto2s1wnm8spbu/Example%20NPKs.rar?dl=0)
## Post #2
- Username: jenny1367
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 19, 2021 3:10 am
- Post datetime: 2023-05-02T06:43:58+00:00
- Post Title: Netease - Identity V | Uncompressed Data Error

Has the same problem here so bumping a bit, I can provide more sample files if needed!
## Post #3
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2023-06-01T08:11:20+00:00
- Post Title: Netease - Identity V | Uncompressed Data Error

I've also got this same problem. I've looked around a lot and according to some posts, Changing the code on line 117 for the NXPK QuickBMS script could possibly fix it, but I've tinkered with it and some recommended values, to no avail.

The code on that line is 'xmath TMP "x - 2"' by default. 250 didn't work and some other values I tried didn't, either. If you ever find a solution to this, Please Please let me know, as I will do the same if I find one ♥
## Post #4
- Username: gardener
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Apr 03, 2023 11:24 am
- Post datetime: 2023-07-07T08:00:21+00:00
- Post Title: Netease - Identity V | Uncompressed Data Error

i have the same issue, hoping someone can help ;;
