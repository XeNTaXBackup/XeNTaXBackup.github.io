## Post #1
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2016-02-24T13:24:15+00:00
- Post Title: [HELP]Sniper Fury Models & Textures (.bre , .dat, .pvr )

Hello guys, aluigi made script that extract .GLA2 of Gameloft, and then there are a folder of meshes (.bre) and a folder of textures (.dat - .pvr ). Can anybody please make some plugins for Noesis or Max? I would appreciate it
Some infomation: [Here](http://zenhax.com/viewtopic.php?t=1468)
Sample: [Here](http://www.mediafire.com/download/64dhudgaja4iuag/0000000e.bre)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-24T19:41:51+00:00
- Post Title: [HELP]Sniper Fury Models & Textures (.bre , .dat, .pvr )

The mesh format is rather simple:



BRES.JPG (84.11 KiB) Viewed 123 times
## Post #3
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2016-02-25T08:22:41+00:00
- Post Title: [HELP]Sniper Fury Models & Textures (.bre , .dat, .pvr )

> Reply from shakotay2
>
> The mesh format is rather simple:
BRES.JPG

Thanks for replying, I had took a look on it in your hex2obj, but i don't have enough skills to make some noesis or max plugins to import it, it would be easily if there was some plugins
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-25T21:09:22+00:00
- Post Title: [HELP]Sniper Fury Models & Textures (.bre , .dat, .pvr )

Maybe some day someone of the  The Usual Suspects will take over that task (or maybe not).
If you can't wait you could try out hex2obj.
For your uploaded bre file be informed that the other submeshes have an FVFsize of 36.

But doesn't make much sense to bother with those six submeshes, imho, since it's circles and some kind of lenses only.

Anyway, here you go (data for 6 H2O files):
0x2f358 768
Vb1
36 24
0x294d8 672
020000
0x0 255

0x343c8 1920
Vb1
36 24
0x2faa8 520
020000
0x0 255

0x38120 1818
Vb1
36 24
0x35420 320
020000
0x0 255

0x39ca8 432
Vb1
36 24
0x390b0 85
020000
0x0 255

0x3bb88 900
Vb1
36 24
0x3a160 186
020000
0x0 255

0x3cfe8 432
Vb1
36 24
0x3c3f0 85
020000
0x0 255
## Post #5
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2016-02-26T05:23:13+00:00
- Post Title: [HELP]Sniper Fury Models & Textures (.bre , .dat, .pvr )

Thanks guy, maybe I should use hex2obj until some plugins were made
