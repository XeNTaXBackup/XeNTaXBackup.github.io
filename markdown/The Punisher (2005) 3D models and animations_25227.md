## Post #1
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-04-06T22:30:58+00:00
- Post Title: The Punisher (2005) 3D models and animations

[https://mega.nz/folder/5SI3FCSD#osuCfihxXjd9pm-uloAVdw](https://mega.nz/folder/5SI3FCSD#osuCfihxXjd9pm-uloAVdw)

*.rxm = basic model
*.rxc = character model
*.dbr/*.rfl = level model
*.rmx = facial animation

I tried both models (punisher_trenchcoat.rxc and wep_remington.rxm), but I got broken faces:



Anyone managed to fix the clumped mesh problem?
## Post #2
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2022-05-03T00:07:12+00:00
- Post Title: The Punisher (2005) 3D models and animations

yeah!! i've always wanted to see the models from this game get ripped!
## Post #3
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2022-06-05T15:57:18+00:00
- Post Title: The Punisher (2005) 3D models and animations

bump!
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2022-07-18T14:07:42+00:00
- Post Title: The Punisher (2005) 3D models and animations

The problem is that the face indices are occasionally repeating, or pointing back to themselves.

See the following from one of the meshes I was looking at:

```
                    FACES
---------------------------------------------

0	( 2,	1,	0 )
1	( 3,	3,	2 )
2	( 6,	5,	4 )
3	( 9,	8,	7 )
4	( 6,	10,	8 )
5	( 11,	4,	10 )
6	( 14,	13,	12 )
7	( 15,	15,	14 )
8	( 16,	17,	16 )
9	( 19,	16,	18 )
10	( 22,	21,	20 )
11	( 24,	23,	21 )
12	( 27,	26,	25 )
13	( 28,	28,	27 )
14	( 31,	30,	29 )
```


Face #1 has 2 repeating indices (3,3). The same for Face #7 (15,15) and Face #8 (16, 16). How to fix this though, is another issue. Any ideas anyone?
## Post #5
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-07-18T14:45:50+00:00
- Post Title: The Punisher (2005) 3D models and animations

> Reply from friendsofwatto ↑Mon Jul 18, 2022 10:07 pm at Mon Jul 18, 2022 10:07 pm
>
> 
Face #1 has 2 repeating indices (3,3)
use Triangle Strip.
bottle.rxm

```
indices num: 130
face Strip num: [4, 4, 5, 10, 10, 4, 3, 10, 8, 8, 8, 4, 4, 4, 4, 4, 4, 4, 4, 5, 4, 4, 4, 3, 4]
(at the end of the file)

vert offset: 5464
vert num: 84
vert stride: 32

*(all value decimal)

```




bottle.rxm.png (3.41 KiB) Viewed 427 times
## Post #6
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-07-23T20:54:24+00:00
- Post Title: The Punisher (2005) 3D models and animations

> Reply from Durik256 ↑Mon Jul 18, 2022 10:45 pm at Mon Jul 18, 2022 10:45 pm
>
> 
friendsofwatto wrote: ↑Mon Jul 18, 2022 10:07 pm
Face #1 has 2 repeating indices (3,3)

use Triangle Strip.
bottle.rxm
Code: Select allindices offset: 640 
indices num: 130
face Strip num: [4, 4, 5, 10, 10, 4, 3, 10, 8, 8, 8, 4, 4, 4, 4, 4, 4, 4, 4, 5, 4, 4, 4, 3, 4]
(at the end of the file)

vert offset: 5464
vert num: 84
vert stride: 32

*(all value decimal)

bottle.rxm.png

I tried the tristrip with hex2obj, but the faces are still broken
So, can you share the Noesis plugin for .rxm and .rxc files?
[bandicam 2022-07-23 13-43-38-932.jpg](https://xentaxbackup.github.io/file/22546_bandicam 2022-07-23 13-43-38-932.jpg)
## Post #7
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-07-25T12:51:07+00:00
- Post Title: The Punisher (2005) 3D models and animations

> Reply from mrmaller1905 ↑Sun Jul 24, 2022 4:54 am at Sun Jul 24, 2022 4:54 am
>
> 
I tried the tristrip with hex2obj, but the faces are still broken
So, can you share the Noesis plugin for .rxm and .rxc files?
*(who said that I made a plugin?)

you even entered the wrong values... (offset and num)
I wrote everything. not all indexes at once:

> Reply from Durik256 ↑Mon Jul 18, 2022 10:45 pm at Mon Jul 18, 2022 10:45 pm
>
> 
Code: Select allface Strip num: [4, 4, 5, 10, 10, 4, 3, 10, 8, 8, 8, 4, 4, 4, 4, 4, 4, 4, 4, 5, 4, 4, 4, 3, 4]
(at the end of the file)



bottle.rxm.gif (45.45 KiB) Viewed 354 times
## Post #8
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-07-25T21:23:06+00:00
- Post Title: The Punisher (2005) 3D models and animations

> Reply from mrmaller1905 ↑Sun Jul 24, 2022 4:54 am at Sun Jul 24, 2022 4:54 am
>
> 
So, can you share the Noesis plugin for .rxm and .rxc files?
today i made a plugin for *.rxm   
[fmt_rxm.py](https://github.com/Durik256/Noesis-Plugins/blob/master/fmt_rxm.py)
## Post #9
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2022-08-12T01:22:31+00:00
- Post Title: The Punisher (2005) 3D models and animations

> Reply from Durik256 ↑Tue Jul 26, 2022 5:23 am at Tue Jul 26, 2022 5:23 am
>
> 
mrmaller1905 wrote: ↑Sun Jul 24, 2022 4:54 am
So, can you share the Noesis plugin for .rxm and .rxc files?

today i made a plugin for *.rxm   
fmt_rxm.py

haha! the script works great!!  any chance of getting the textures / character models to work??
## Post #10
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-08-21T14:21:14+00:00
- Post Title: The Punisher (2005) 3D models and animations

> Reply from mrmaller1905 ↑Thu Apr 07, 2022 6:30 am at Thu Apr 07, 2022 6:30 am
>
> 
*.rmx = facial animation
i made plugins for *.vpp (game archive), *.rxm (static model), *.rxc (character model), *.ceg (texture container)
[link plugins [github *.rxm]](https://github.com/Durik256/Noesis-Plugins/blob/master/fmt_rxm.py)
[link on boosty [all plugins]](https://boosty.to/durik256/posts/a29c9a1a-5f17-41b4-b6af-107786a34360)
[2a97e78c15efcb6c9.png](https://xentaxbackup.github.io/file/22674_2a97e78c15efcb6c9.png)
## Post #11
- Username: Raphael Splinterson
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 31, 2016 12:36 pm
- Post datetime: 2022-08-25T21:38:55+00:00
- Post Title: The Punisher (2005) 3D models and animations

> Reply from Durik256 ↑Sun Aug 21, 2022 10:21 pm at Sun Aug 21, 2022 10:21 pm
>
> 
mrmaller1905 wrote: ↑Thu Apr 07, 2022 6:30 am
*.rmx = facial animation

i made plugins for *.vpp (game archive), *.rxm (static model), *.rxc (character model), *.ceg (texture container)

This is wonderful. Will you publish a new version of the plugin?
## Post #12
- Username: y2keeth
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Sep 19, 2021 5:36 pm
- Post datetime: 2022-10-10T04:49:27+00:00
- Post Title: The Punisher (2005) 3D models and animations

> Reply from Durik256 ↑Sun Aug 21, 2022 10:21 pm at Sun Aug 21, 2022 10:21 pm
>
> 
mrmaller1905 wrote: ↑Thu Apr 07, 2022 6:30 am
*.rmx = facial animation

i made plugins for *.vpp (game archive), *.rxm (static model), *.rxc (character model), *.ceg (texture container)

can we have them too?
please
## Post #13
- Username: y2keeth
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Sep 19, 2021 5:36 pm
- Post datetime: 2023-03-17T01:37:12+00:00
- Post Title: The Punisher (2005) 3D models and animations

guess not damn
