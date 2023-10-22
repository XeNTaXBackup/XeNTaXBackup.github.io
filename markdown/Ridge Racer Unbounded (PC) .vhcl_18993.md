## Post #1
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2018-10-29T02:32:07+00:00
- Post Title: Ridge Racer Unbounded (PC) .vhcl

After looking through this game, I was able to rip the textures no problem as the .bmap files hold DDS files, but i've been having trouble with the .vhcl formats.

While I was able to get something with the vertices (maybe? Even this may not be correct), the faces don't seem work at all while using Model Researcher.



Can anyone help me with this format? There's a few cars i'm really wanting to get the models from, and your help would be greatly appreciated!

I've added a few samples as well. Thank you!

[https://www.sendspace.com/file/r6o4dp](https://www.sendspace.com/file/r6o4dp)
[https://www.sendspace.com/file/dutwno](https://www.sendspace.com/file/dutwno)
[https://www.sendspace.com/file/octo9g](https://www.sendspace.com/file/octo9g)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-29T13:09:11+00:00
- Post Title: Ridge Racer Unbounded (PC) .vhcl

It's a matter of endianness, it's big endian here:



body-vhcl.png (142.99 KiB) Viewed 374 times


(I'm more familiar with hex2obj, so I used that.)
## Post #3
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2018-10-29T18:05:24+00:00
- Post Title: Ridge Racer Unbounded (PC) .vhcl

That was the trick, thank you! It's funny too, cause I tried Big Endian before. I guess I was going the wrong way about it, haha.



Thanks a lot!
## Post #4
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-01-25T14:28:27+00:00
- Post Title: Ridge Racer Unbounded (PC) .vhcl

anyone have any luck in converting the vhcl with texture bmap files? it's for PC version
zip file inside with samples link:
[https://mega.nz/file/4aIFkZCB#mFfPLM486 ... Mghz1B905U](https://mega.nz/file/4aIFkZCB#mFfPLM486-TZ5pAKsLsUDpyoYJv3f40p6Mghz1B905U)

also if anyone manages to find any model/texture extractor tool or blender, noesis plugin, it's highly appreciated to post it in.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-01-25T20:12:18+00:00
- Post Title: Ridge Racer Unbounded (PC) .vhcl

Using hex2obj (view link in my sig),
first submesh only:
-



body_vhcl.jpg (197.83 KiB) Viewed 269 times
## Post #6
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-01-26T04:11:51+00:00
- Post Title: Ridge Racer Unbounded (PC) .vhcl

> Reply from UB833 ↑Wed Jan 25, 2023 10:28 pm at Wed Jan 25, 2023 10:28 pm
>
> 
texture bmap

i made plugin for bmap texture
[tex_bmap.py](https://github.com/Durik256/Noesis-Plugins/blob/master/tex_bmap.py)
## Post #7
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2023-01-26T18:59:07+00:00
- Post Title: Ridge Racer Unbounded (PC) .vhcl

If I load all subobjects, it seems all models centered at 0,0,0.



Ridge_Racer_Unbounded.png (95.4 KiB) Viewed 239 times
## Post #8
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-03-03T04:23:28+00:00
- Post Title: Ridge Racer Unbounded (PC) .vhcl

I can provide more samples to make this topic active again. The texture part I have no problem with it because Durik256 made an exporter for noesis as shown in the above post.
More sample link:
[https://mega.nz/file/IaZDjbDK#teIYzWaTa ... k3z0UGe1F0](https://mega.nz/file/IaZDjbDK#teIYzWaTaduKuftLLEO0YpmSWhNuUHq-ck3z0UGe1F0)
## Post #9
- Username: arminm74
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 28, 2023 6:42 am
- Post datetime: 2023-03-28T13:34:41+00:00
- Post Title: Ridge Racer Unbounded (PC) .vhcl

hi everyone;
I want to extract 3d models of this game but i can't . 
( I don't know any tool for this ; just unpakke that it's Useless for be, because I cant run a app with cmd  ) . 
I want to know how did you can get cars 3d model ? 
if you use unpakke , please teach me how to run it with cmd ; and if there is another program / tool , please tell me 
(I searched in internet but I found nothing )
I realy need these 3d models ; if someone help me , I will be Grateful
## Post #10
- Username: SallyArts
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Feb 13, 2021 6:19 am
- Post datetime: 2023-07-29T21:45:44+00:00
- Post Title: Ridge Racer Unbounded (PC) .vhcl

> Reply from shakotay2 ↑Thu Jan 26, 2023 4:12 am at Thu Jan 26, 2023 4:12 am
>
> 
Using hex2obj (view link in my sig),
first submesh only:
-
body_vhcl.jpg

do you mind me asking amore about the uvs? those got me interested about
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-29T23:12:50+00:00
- Post Title: Ridge Racer Unbounded (PC) .vhcl

> Reply from SallyArts ↑Sun Jul 30, 2023 5:45 am at Sun Jul 30, 2023 5:45 am
>
> 
do you mind me asking amore about the uvs? those got me interested aboutWere given in the post you quoted: uvpos= 12
## Post #12
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-07-30T10:46:04+00:00
- Post Title: Ridge Racer Unbounded (PC) .vhcl

> Reply from Nega ↑Mon Oct 29, 2018 10:32 am at Mon Oct 29, 2018 10:32 am
>
> 
the .vhcl formats.

> Reply from UB833 ↑Fri Mar 03, 2023 12:23 pm at Fri Mar 03, 2023 12:23 pm
>
> 
because Durik256 made an exporter for noesis

> Reply from arminm74 ↑Tue Mar 28, 2023 9:34 pm at Tue Mar 28, 2023 9:34 pm
>
> 
 I will be Grateful

> Reply from SallyArts ↑Sun Jul 30, 2023 5:45 am at Sun Jul 30, 2023 5:45 am
>
> 
about the uvs?

i made plugin for Noesis for *.vhcl and *.bmap
*(as usual, I'm too lazy to read the format, so "i search for key bytes")



body.vhcl.png (31.3 KiB) Viewed 123 times


[fmt_vhch.py](https://github.com/Durik256/Noesis-Plugins/blob/master/fmt_vhch.py)
[tex_bmap.py](https://github.com/Durik256/Noesis-Plugins/blob/master/tex_bmap.py)
## Post #13
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-30T11:04:45+00:00
- Post Title: Ridge Racer Unbounded (PC) .vhcl

> Reply from Durik256 ↑Sun Jul 30, 2023 6:46 pm at Sun Jul 30, 2023 6:46 pm
>
> 
Nega wrote: ↑Mon Oct 29, 2018 10:32 am
the .vhcl formats.

UB833 wrote: ↑Fri Mar 03, 2023 12:23 pm
because Durik256 made an exporter for noesis

arminm74 wrote: ↑Tue Mar 28, 2023 9:34 pm
 I will be Grateful

SallyArts wrote: ↑Sun Jul 30, 2023 5:45 am
about the uvs?


i made plugin for Noesis for *.vhcl and *.bmap
*(as usual, I'm too lazy to read the format, so "i search for key bytes")
body.vhcl.png
fmt_vhch.py
tex_bmap.py

a huge thx btw. Gonna download the game and use it for my  nfs games car modding
## Post #14
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-10-21T09:40:40+00:00
- Post Title: Ridge Racer Unbounded (PC) .vhcl

btw I've been searching for other tools and I think I've found an alternative tool for bmap textures in discord server.

[https://drive.google.com/file/d/1SSgY9s ... g-vfA/edit](https://drive.google.com/file/d/1SSgY9s1LG2vsfFlwl0oBL5jyPg9g-vfA/edit)
