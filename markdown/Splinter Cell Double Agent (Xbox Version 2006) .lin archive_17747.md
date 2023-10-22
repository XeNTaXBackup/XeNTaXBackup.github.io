## Post #1
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-02-25T17:20:56+00:00
- Post Title: Splinter Cell: Double Agent (Xbox Version 2006) .lin archive

Hello, everyone! I came here today wondering how can I extract the files from this awesome game! 
The formats are .lin from what I can see. 
I uploaded an archive (link is in the word "archive") with some samples. Any ideas? I tried using Umodel and DecUbi, but to no avail..

Edit:

```

get ARC_SZ asize
get NAME basename
get EXT extension
string NAME + _decomp.
string NAME + EXT
do
   get SIZE long
   get ZSIZE long
   savepos OFFSET
   append
   clog NAME OFFSET ZSIZE SIZE
   append
   math OFFSET + ZSIZE
   goto OFFSET
while OFFSET != ARC_SZ 
```


With this code, you can decompress the map files, but then you get something like [this](https://www.dropbox.com/s/i07rk5q64ng7g2d/x12_ny_a_decomp.lin?dl=0). I don't know what to do.
## Post #2
- Username: 3A2watup
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 16, 2018 8:04 am
- Post datetime: 2018-12-03T15:14:49+00:00
- Post Title: Splinter Cell: Double Agent (Xbox Version 2006) .lin archive

Have you progressed in this?
I'm really interested in animations from this game.
## Post #3
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-03-18T20:45:00+00:00
- Post Title: Splinter Cell: Double Agent (Xbox Version 2006) .lin archive

I would give up in your place. LIN file holds data in the same way as Xbox would keeps it in memory - for direct calls purpose.
## Post #4
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-03-18T21:50:06+00:00
- Post Title: Splinter Cell: Double Agent (Xbox Version 2006) .lin archive

> Reply from VendorX ↑Sat Mar 19, 2022 4:45 am at Sat Mar 19, 2022 4:45 am
>
> 
I would give up in your place. LIN file holds data in the same way as Xbox would keeps it in memory - for direct calls purpose.

Well then. What's the BMS script to decompile the LIN Files?
## Post #5
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-03-18T23:35:53+00:00
- Post Title: Splinter Cell: Double Agent (Xbox Version 2006) .lin archive

You should have more luck with PC version of this game.

Update:
pc game.umd is a standard Unreal Engine UMD v2 file (not compressed or encrypted). Just bunch of configuration files and content packages names.
System\Linear\pc holds content (ZLIB compressed *.LIN) files except for sonds. Content files keeps .lin extension so they didn't change its format.
