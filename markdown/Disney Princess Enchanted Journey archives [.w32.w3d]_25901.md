## Post #1
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2022-10-12T14:21:15+00:00
- Post Title: Disney Princess Enchanted Journey archives [.w32/.w3d]

Could anyone here take a look at these? Wanted to rip the ballroom from Beauty and the Beast as well as the seven dwarfs' cottage for a Guitar Hero World Tour mod or two.

[https://www2.zippyshare.com/v/wRCZTX0e/file.html](https://www2.zippyshare.com/v/wRCZTX0e/file.html)

If I'm not mistaken some dude managed to modify at least some of the files for a widescreen mod for this game, but it may have been just a hex edit of some kind.
## Post #2
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2022-10-13T02:56:04+00:00
- Post Title: Disney Princess Enchanted Journey archives [.w32/.w3d]

Anyone?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-14T12:16:46+00:00
- Post Title: Disney Princess Enchanted Journey archives [.w32/.w3d]

(zippyshare is not valid in my country...)
## Post #4
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2022-10-14T12:47:15+00:00
- Post Title: Disney Princess Enchanted Journey archives [.w32/.w3d]

> Reply from shakotay2 ↑Fri Oct 14, 2022 8:16 pm at Fri Oct 14, 2022 8:16 pm
>
> 
(zippyshare is not valid in my country...)

OK, try this one:
[https://drive.google.com/file/d/1Dw1kZk ... sp=sharing](https://drive.google.com/file/d/1Dw1kZkERfhgINl99pKVa3zmQ7-0m9RuB/view?usp=sharing)
[https://www.strawberryforum.org/techknow/levels.7z](https://www.strawberryforum.org/techknow/levels.7z)

.w3d seems to be loose geometry or a dictionary of models, idk. What I am sure is that the files named _t.w32 contains uncompressed BGRA 8888 textures:


...the other files I am not sure of, maybe they do contain terrain or other level geometry.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-14T16:39:20+00:00
- Post Title: Disney Princess Enchanted Journey archives [.w32/.w3d]

Thx; got some structure (too tired to search for face indices (FIs), so used auto created ones):
.



I_snwt-w32.jpg (88.36 KiB) Viewed 103 times

If you use 1000 as vertex count you get some funny monster. But too weird to use the mesh without the original FIs.
## Post #6
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2022-10-14T21:07:14+00:00
- Post Title: Disney Princess Enchanted Journey archives [.w32/.w3d]

> Reply from shakotay2 ↑Sat Oct 15, 2022 12:39 am at Sat Oct 15, 2022 12:39 am
>
> 
Thx; got some structure (too tired to search for face indices (FIs), so used auto created ones):
.
I_snwt-w32.jpgIf you use 1000 as vertex count you get some funny monster. But too weird to use the mesh without the original FIs.

Did you try it on the w3d files?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-14T22:00:23+00:00
- Post Title: Disney Princess Enchanted Journey archives [.w32/.w3d]

nope. Maybe it's compressed data.
## Post #8
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2022-10-14T23:57:53+00:00
- Post Title: Disney Princess Enchanted Journey archives [.w32/.w3d]

> Reply from shakotay2 ↑Sat Oct 15, 2022 6:00 am at Sat Oct 15, 2022 6:00 am
>
> 
nope. Maybe it's compressed data.

Those are meshes themselves. They're not compressed as they shrink down in size when you zip them.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-15T07:27:37+00:00
- Post Title: Disney Princess Enchanted Journey archives [.w32/.w3d]

> Reply from huckleberrypie ↑Sat Oct 15, 2022 7:57 am at Sat Oct 15, 2022 7:57 am
>
> 
They're not compressed as they shrink down in size when you zip them.haha, you got a point. Nevertheless I can't get a decent point cloud from .w3d.
## Post #10
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2022-10-15T08:48:03+00:00
- Post Title: Disney Princess Enchanted Journey archives [.w32/.w3d]

> Reply from shakotay2 ↑Sat Oct 15, 2022 3:27 pm at Sat Oct 15, 2022 3:27 pm
>
> 
huckleberrypie wrote: ↑Sat Oct 15, 2022 7:57 am
They're not compressed as they shrink down in size when you zip them.
haha, you got a point. Nevertheless I can't get a decent point cloud from .w3d.

Damn, looks like I'm SOL here.
