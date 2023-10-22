## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-09-12T16:39:23+00:00
- Post Title: Full Auto 2: Battlelines - music deinterlacer

Deinterlacer tool for Full Auto 2: Battlelines - music

Use this on YUK files. Then you can add WAV headers with alpha23's script and decode/play them if you have atrac3 codec installed.

It seems only this game have this strange kind of interleave. There are 0x6000 blocks and 8 stereo tracks. But in the end, the remaining part is added to the last 0x6000 block and then split into 2 parts. These parts may be equal (if they have even number of samples), or first part will be smaller.

Example: YUK file 0x0103b000 length.
It will be split like this:

```
0x6000 0x6000 0x6000 0x6000 0x6000 0x6000 0x6000 0x6000
0x6000 0x6000 0x6000 0x6000 0x6000 0x6000 0x6000 0x6000
0x6000 0x6000 0x6000 0x6000 0x6000 0x6000 0x6000 0x6000
...
0x6000 0x6000 0x6000 0x6000 0x6000 0x6000 0x6000 0x6000
0x6000 0x6000 0x6000 0x6000 0x6000 0x6000 0x6000 0x6000
0x5B80 0x5B80 0x5B80 0x5B80 0x5B80 0x5B80 0x5B80 0x5B80 
0x5D00 0x5D00 0x5D00 0x5D00 0x5D00 0x5D00 0x5D00 0x5D00
```

[fullauto2_deint.rar](https://xentaxbackup.github.io/file/9727_fullauto2_deint.rar)
