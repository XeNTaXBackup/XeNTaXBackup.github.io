## Post #1
- Username: hondacrx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 17, 2017 6:22 pm
- Post datetime: 2017-06-17T10:46:12+00:00
- Post Title: ©v·Ú4%¦×Qã.¶Y$¢¾Ý˜Iÿiõ«RÇO—Zõ9Ÿ5ž¿U¥Òå£„hµ¿Ãžº@KÞY×sÍ\Åýó

Æ¥…Yv]_”µ!ë«³%õ±eÞ.v;w¤Ç}L4c·õ!43]¢(#âòãhW¦¸çzcfÝØÇï`dÏ
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-17T15:53:48+00:00
- Post Title: ©v·Ú4%¦×Qã.¶Y$¢¾Ý˜Iÿiõ«RÇO—Zõ9Ÿ5ž¿U¥Òå£„hµ¿Ãžº@KÞY×sÍ\Åýó

You didn't tell where the "proper co-ordinates" of the Unique objects to be found.

Anyways, since you seem to know how to place them, after a glance at t_ginza.hood:

there's t_ginza_rd_48_x, unique_component 0, it's the owner of 
instance_component 1253 for example (and 4 other instances)

I assume, that instance has the (relative?) position -270.760834	0.195346	271.849213.
So I guess you need to place that instance relative to it's owner (whose position you know from what you wrote).

InstancePos = ownerPos + relPos (vectors)
