## Post #1
- Username: watty256
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Apr 12, 2017 4:29 pm
- Post datetime: 2021-02-24T17:43:41+00:00
- Post Title: Lumberyard .Actor File

Is there any way to extract the mesh from this file format I believe there to be a steering wheel in there somewhere?


Here is the file
[https://mega.nz/file/pPQR0Q4A#5BzoVTUXw ... b48y5LXHRE](https://mega.nz/file/pPQR0Q4A#5BzoVTUXwmQQYEpDYkRMYmoqzlNhPPTvEb48y5LXHRE)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-24T18:39:07+00:00
- Post Title: Lumberyard .Actor File

On a quick glance I get this (and a 2nd for correction  ):
.



for_cortinamk3_72_actor-actor.png (39.23 KiB) Viewed 54 times


(face indices at 0xa10, count 2472 were not suiting)
Thx to Bigchillghost.
## Post #3
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-02-24T19:40:59+00:00
- Post Title: Lumberyard .Actor File

Yretenai made a noesis plugin for Lumberyard. You can probably check the code [viewtopic.php?f=16&t=22278](https://forum.xentax.com/viewtopic.php?f=16&t=22278)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-24T21:54:52+00:00
- Post Title: Lumberyard .Actor File

cool!   a dll WITH source!

But said model "casts" an error though:

[dragon_lumberyard][dragon::lumberyard::Actor::Actor] Found Info
[dragon_lumberyard][dragon::lumberyard::Actor::Actor] Chunk Id is out range, aborting.
## Post #5
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-02-25T10:00:46+00:00
- Post Title: Lumberyard .Actor File

> Reply from shakotay2 ↑Thu Feb 25, 2021 5:54 am at Thu Feb 25, 2021 5:54 am
>
> 
cool!   a dll WITH source!
Indeed !

> Reply from shakotay2 ↑Thu Feb 25, 2021 5:54 am at Thu Feb 25, 2021 5:54 am
>
> 
But said model "casts" an error though:

[dragon_lumberyard][dragon::lumberyard::Actor::Actor] Found Info
[dragon_lumberyard][dragon::lumberyard::Actor::Actor] Chunk Id is out range, aborting.

Yes I noticed that too, I posted the link so the op could check the code and make educated guesses to make it compatible with his model. I think it was only tested on Crucible.
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-02-25T12:23:26+00:00
- Post Title: Lumberyard .Actor File

> Reply from shakotay2 ↑Thu Feb 25, 2021 2:39 am at Thu Feb 25, 2021 2:39 am
>
> 
Faces are weird, switching to strips doesn't cure it, nor the use of backface culling.
You were just using the wrong indices.



for_cortinamk3_72_actor.png (108.18 KiB) Viewed 60 times
## Post #7
- Username: watty256
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Apr 12, 2017 4:29 pm
- Post datetime: 2021-02-25T17:55:50+00:00
- Post Title: Lumberyard .Actor File

Thank you everybody for you help it is much appreciated.
