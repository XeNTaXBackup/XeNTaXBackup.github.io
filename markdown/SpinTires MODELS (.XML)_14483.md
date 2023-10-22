## Post #1
- Username: Verit0z
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 15, 2013 4:34 am
- Post datetime: 2016-06-19T01:39:59+00:00
- Post Title: SpinTires MODELS (.XML)

MODELS FROM SPINTIRES


How can I export these to .obj? These vehicle models are all in .XML files.

They do have a model viewer, however there is no export options. If someone could tell me how I can take said .XML files and import to blender, max, milkshape any real modeling program, and convert to .obj etc, that'd be great!


[http://spintires.lt/chevy-k10-82-spintires-03-03-16/](http://spintires.lt/chevy-k10-82-spintires-03-03-16/)

Sample of .xml
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-06-19T02:24:01+00:00
- Post Title: SpinTires MODELS (.XML)

wheels_7oqkocc3



wheels_7oqkocc3.png (67.05 KiB) Viewed 320 times
## Post #3
- Username: Verit0z
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 15, 2013 4:34 am
- Post datetime: 2016-06-19T02:36:46+00:00
- Post Title: SpinTires MODELS (.XML)

> Reply from AceWell
>
> wheels_7oqkocc3
wheels_7oqkocc3.png
How much
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-06-19T04:01:09+00:00
- Post Title: SpinTires MODELS (.XML)

Nothing, just a little time to understand it, Hex2obj is free for every one to use   

from that sample i posted before
0x0 - length of xml data
0x11a - num submeshes(?)
0x1B1 - num triangles (multiply by 3 to get face count)
0x1B9 - vertex count

ive seen 3 different vertex strides in various samples so far 
24,28,32
i guess there is a flag indicating these since i can't find them outright
## Post #5
- Username: Verit0z
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 15, 2013 4:34 am
- Post datetime: 2016-06-19T05:10:48+00:00
- Post Title: SpinTires MODELS (.XML)

> Reply from AceWell
>
> Nothing, just a little time to understand it, Hex2obj is free for every one to use   

from that sample i posted before
0x0 - length of xml data
0x122 - num submeshes?
0x1B1 - num triangles (multiply by 3 to get face count)
0x1B9 - vertex count

ive seen 3 different vertex strides in various samples so far 
24,28,32
i guess there is a flag indicating these since i can't find them outright

Will pay anyone a hefty amount, if they can make a easy to use tool. I'm lazy, I can't code, but I can pay. lmao.


edit; Even for a .XML to .X format...
Or it'd be cool to do it that way. Can't find many in .x format.
By pay I don't mean like a five year old, "heres $20" ..500+ depending on time and difficulty, I can get the ones in .x format, but the other models which are in .XML I can't easy import. lol
