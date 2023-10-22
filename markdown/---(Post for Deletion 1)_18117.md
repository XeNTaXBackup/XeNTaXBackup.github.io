## Post #1
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2018-05-20T21:43:30+00:00
- Post Title: ---(Post for Deletion 1)

---
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-21T10:21:29+00:00
- Post Title: ---(Post for Deletion 1)

howfie released the sourec of his tool in this thread:
[viewtopic.php?f=16&t=11681&hilit=macross](http://forum.xentax.com/viewtopic.php?f=16&t=11681&hilit=macross)

You'll need include files (X_GAME library?) to get it compiled.

As I wrote 4 years ago I did't dig too deep into this since my konig tool achieved good results
(maybe not as good as howfie's tool but most models look the same in blender).

The problem of the clumped submeshes could be solved using a table of position offsets.
But the possible one in the mb_300.mdl looks to irregular than to waste time with it.

edit: well, I couldn't resist trying the offsets below but got sorta exploding model only.
They looked promising, though, since there's symmetrical values, too:
# 0.000000 15.805248 -20.581451 
# 0.000000 0.000000 0.000000 
# 0.000000 0.000000 0.000000 
# 0.014371 18.244659 1.000915 
# 0.000000 0.000000 0.000000 
# 0.000000 0.000000 0.000000 
# 0.016989 1.624128 -0.071842 
# -0.031360 3.293288 -3.928927 
# 0.000000 -16.916716 -9.436964 
# -0.031359 2.273794 -0.745130 
# 0.000000 1.739621 -0.041571 
# 0.000000 0.000000 0.000000 
# 0.000000 0.000000 0.000000 
# 0.000000 0.359996 0.301729 
# -0.875000 0.000000 0.000000 
# -0.033143 0.000000 4.426728 
# 0.875000 0.000000 0.000000 
# 0.033250 0.000000 4.426728 
# -0.029322 3.887945 -2.777696 
# 2.663500 0.216546 0.639022 
# -2.664193 0.193253 0.646591 
# -0.002037 0.875563 -0.386855 
# 0.002037 -0.219815 -4.535990 
# 0.000000 -0.358744 -1.320225 
# -4.172159 26.345882 0.000000 
# 1.181332 -0.037049 0.000000 
# -1.181250 -0.037049 0.000000 
# 1.181332 -1.488401 0.000000 
# -1.181250 -1.488401 0.000000 
# 1.308290 -0.771437 3.827960 
# 1.308290 -0.771437 -3.832787 
# -1.220598 -0.771437 3.827960 
# -1.220598 -0.771437 -3.83278
...

So you may be better off looking in the concerning tbl file where strings like
mb300_00, mb300_88, mb300_98, mb300_fullburst
reside. Could be submesh names and maybe there's the offsets, too.

Didn't find big endian floats, so maybe it's shorts.
