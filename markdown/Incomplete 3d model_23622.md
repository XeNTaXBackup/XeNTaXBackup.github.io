## Post #1
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-03-23T16:46:57+00:00
- Post Title: Incomplete 3d model

Helloo! I was trying to extract the model inside this .modl file, I was able to get a part of the body with hex2obj, but it was incomplete and without head. It seems that the file contains bone references but well it will be the next step, for the moment I want to get the entire model, maybe someone could check the file, maybe I'm just not doing right. Thanks .   

[https://www.mediafire.com/file/u83rf94b ... .modl/file](https://www.mediafire.com/file/u83rf94bbtxi48g/2303429.modl/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-23T17:38:18+00:00
- Post Title: Incomplete 3d model

> Reply from moonpaladin ↑Wed Mar 24, 2021 12:46 am at Wed Mar 24, 2021 12:46 am
>
> for the moment I want to get the entire model, maybe someone could check the file, maybe I'm just not doing right. Thanks .I don't see the problem, it's just some work to do.   If you don't want to get the whole format specs you'll need some rules (created by yourself) at least or a magic table with counts or something like that.
.



2303429-modl.png (118.03 KiB) Viewed 66 times
## Post #3
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-03-23T19:04:48+00:00
- Post Title: Incomplete 3d model

woaaaaaa! I'm gonna try to get it this time! thanks Shakotay
## Post #4
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-03-23T19:08:24+00:00
- Post Title: Incomplete 3d model

> Reply from shakotay2 ↑Wed Mar 24, 2021 1:38 am at Wed Mar 24, 2021 1:38 am
>
> 
moonpaladin wrote: ↑Wed Mar 24, 2021 12:46 amfor the moment I want to get the entire model, maybe someone could check the file, maybe I'm just not doing right. Thanks .I don't see the problem, it's just some work to do.   If you don't want to get the whole format specs you'll need some rules (created by yourself) at least or a magic table with counts or something like that.
.
2303429-modl.png
By the wayyyy how about the uv block? because the body part that I get didn't have the uv map I tried with some values in the uv block but them failed x.x. I totally forgot to ask about that at the beginning, because it was something that I was also missing.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-23T19:45:52+00:00
- Post Title: Incomplete 3d model

> Reply from moonpaladin ↑Wed Mar 24, 2021 3:08 am at Wed Mar 24, 2021 3:08 am
>
> I tried with some values in the uv block but them failed x.x.well, how about gaining some basics instead of brute force trying?   (modulo 4 for floats didn't you know?)
It's 28-8 for the head so use 20.
