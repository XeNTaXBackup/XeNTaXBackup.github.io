## Post #1
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-04-21T09:56:12+00:00
- Post Title: Demon Stone model *.XBG

I get mesh, but i see bad mesh:
[Sorcerer.jpg](https://xentaxbackup.github.io/file/10810_Sorcerer.jpg)
## Post #2
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-04-21T09:57:24+00:00
- Post Title: Demon Stone model *.XBG

Start Index +0x3000. Start Vertex +0x4DC0. Vertex stride 0x40
File this model:
[Sorcerer.rar](https://xentaxbackup.github.io/file/10811_Sorcerer.rar)
## Post #3
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-04-21T10:03:59+00:00
- Post Title: Demon Stone model *.XBG

Indices 16 bit.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-21T16:34:48+00:00
- Post Title: Demon Stone model *.XBG

first submesh, tristripped face indices:



Sorcerer.jpg (168.05 KiB) Viewed 119 times
## Post #5
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-04-21T16:50:28+00:00
- Post Title: Demon Stone model *.XBG

Thanks.

> tristripped face indices
You mean quad indices ?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-21T17:06:07+00:00
- Post Title: Demon Stone model *.XBG

nope. Google for 'triangle strips'.
## Post #7
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-04-21T17:34:26+00:00
- Post Title: Demon Stone model *.XBG

Thanks !
Now mesh draw correct.
[sor.jpg](https://xentaxbackup.github.io/file/10813_sor.jpg)
## Post #8
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-04-26T08:38:37+00:00
- Post Title: Demon Stone model *.XBG

```
offset 4	(2,)
offset 8	(50, 26)
offset 12	(1.0, 1.0, 1.0, 1.0, 3.0)
offset 48	(64, 204-offset to info section, 873, 184)
offset 64	(3, 3, 0, 0, 2, 0, 80, 0, 0, 0)

offset 204	(0, 3)
offset 208	(236,)-offset to mesh info

offset 212	(2, 1)
offset 216	(437,)-offset to mesh info
offset 220	(3, 1)
offset 224	(489,)-offset to mesh info
offset 228	(3, 1)
offset 232	(541,)-offset to mesh info

#mesh count = 3

offset 236	(1, 0, 24, 3801-indice count)
offset 244	(1464-vert count, 320, 12288-indice stream offset, 19904-vert stream offset, 344)
offset 264	(1, 0, 24, 1741)
offset 272	(647, 364, 113600, 117088, 388)
offset 292	(1, 0, 9, 203)
offset 300	(68, 408, 158496, 158912, 417)

#next 3 meshes

offset 437	(1, 0, 4, 1095, 350-indice count, 0)
offset 449	(465, 163264-indice stream offset, 165456-vert stream offset, 469)
offset 465	(4880, 5396)
offset 489	(1, 0, 4, 2315, 768, 0)
offset 501	(517, 187856, 192496, 521)
offset 517	(4880, 5396)
offset 541	(1, 0, 4, 2463, 891, 14)
offset 553	(569, 241648, 246576, 573)
offset 569	(4880, 5396)

```

[screen.jpg](https://xentaxbackup.github.io/file/10838_screen.jpg)
## Post #9
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-04-26T11:04:37+00:00
- Post Title: Demon Stone model *.XBG

Szkaradek123
You script for blender ?
