## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2019-11-14T21:45:18+00:00
- Post Title: 封神召唤师 - God Summoner (*.sm, *.skel, *.anim)

Hey everyone. Can someone help to make 3DMax or Noesis script for loading models from this games? I've uploaded archive with sample files.



```
skel - Skeleton
sm - Mesh ???
vsm - Mesh settings (xml)
```


Samples: > [here (~200mb)](https://www75.zippyshare.com/v/OJzAg0U7/file.html)

I will be grateful! Thanks advance!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-17T07:40:02+00:00
- Post Title: 封神召唤师 - God Summoner (*.sm, *.skel, *.anim)

(zippyshare is not accessible in my country...)
## Post #3
- Username: outlawer1545
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 17, 2019 1:12 pm
- Post datetime: 2019-11-17T08:14:28+00:00
- Post Title: 封神召唤师 - God Summoner (*.sm, *.skel, *.anim)

you can acces with umodel viewer
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2019-11-17T09:54:06+00:00
- Post Title: 封神召唤师 - God Summoner (*.sm, *.skel, *.anim)

> Reply from shakotay2 ↑Sun Nov 17, 2019 3:40 pm at Sun Nov 17, 2019 3:40 pm
>
> 
(zippyshare is not accessible in my country...)
Woops  . How about mediafire ? > [here](https://www.mediafire.com/file/x9yuj1amcpl9jl7/samples.zip/file) or Google Drive [here](https://drive.google.com/file/d/1B7kbCCXn7cnH1pEqDbejOsqnFUVVyrzY/view?usp=sharing)

> Reply from outlawer1545 ↑Sun Nov 17, 2019 4:14 pm at Sun Nov 17, 2019 4:14 pm
>
> 
you can acces with umodel viewer
Nah. This game is not on the Unreal Engine
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-17T10:53:01+00:00
- Post Title: 封神召唤师 - God Summoner (*.sm, *.skel, *.anim)

Using hex2obj (view link in my sig):
.



f01_1a-sm.png (101.42 KiB) Viewed 554 times


It's only usable for extracting meshes. As a first approach, for several submeshes you'd need a script/tool.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-17T11:23:06+00:00
- Post Title: 封神召唤师 - God Summoner (*.sm, *.skel, *.anim)

chiyou01.skin:
.



chiyou01-skin.png (66.67 KiB) Viewed 551 times
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2019-11-19T21:47:38+00:00
- Post Title: 封神召唤师 - God Summoner (*.sm, *.skel, *.anim)

So, can someone write a script to load these files into Noesis or 3D Max?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-20T11:29:09+00:00
- Post Title: 封神召唤师 - God Summoner (*.sm, *.skel, *.anim)

well, I know you guys like scripts  For me it's easier to do it with 'C', see my updated Make_obj project (source & exe) here:

> Reply from shakotay2 ↑Mon Mar 06, 2017 6:01 pm at Mon Mar 06, 2017 6:01 pm
>
> 
.



f57_b.jpg (163.89 KiB) Viewed 506 times

As always: use this on your own risk!

Tested with f57_b.sm and f01_1a.sm only. So could fail with other sm files!
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2019-11-21T13:45:32+00:00
- Post Title: 封神召唤师 - God Summoner (*.sm, *.skel, *.anim)

Plugin for Blender also will be great
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-21T16:42:47+00:00
- Post Title: 封神召唤师 - God Summoner (*.sm, *.skel, *.anim)

Of course. (But I'm a blender script patcher only, not a creator  ).

I've updated the Make_obj project to handle .skin now (hero10b_01.skin and leizhenzi03.skin tested only):
.



leizhenzi03_skin.png (86.35 KiB) Viewed 469 times
## Post #11
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2019-11-22T16:19:33+00:00
- Post Title: 封神召唤师 - God Summoner (*.sm, *.skel, *.anim)

[https://zenhax.com/viewtopic.php?f=5&t= ... 220#p52220](https://zenhax.com/viewtopic.php?f=5&t=12801&p=52220#p52220)
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-22T17:14:15+00:00
- Post Title: 封神召唤师 - God Summoner (*.sm, *.skel, *.anim)

thanks, Mariusz!
(I always knew something went wrong with my skin to obj conversion - see my previous post)
.



leizhenzi03-skin.png (91.47 KiB) Viewed 443 times
## Post #13
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-11-22T17:57:28+00:00
- Post Title: 封神召唤师 - God Summoner (*.sm, *.skel, *.anim)

The game's assets are compressed into an archive containing a CTC header called "data0.mp3", how did you unpack it?
There are games that unpack assets when the game runs, but this game doesn't seem to do that...
## Post #14
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-12-10T05:35:32+00:00
- Post Title: 封神召唤师 - God Summoner (*.sm, *.skel, *.anim)

If I don't misunderstood the "封神召唤师" as another game, the game of "启源女神" uses the same CTC header data0.mp3.
They have more beautiful graphics and models.
[http://a.4399.cn/mobile/148377.html](http://a.4399.cn/mobile/148377.html)

I don't know how to uncompress CTC header mp3 containers, so I don't know if * .sm, * .skel, * .anim are included.
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-11T12:41:20+00:00
- Post Title: 封神召唤师 - God Summoner (*.sm, *.skel, *.anim)

> Reply from einherjar007 ↑Sat Nov 23, 2019 1:57 am at Sat Nov 23, 2019 1:57 am
>
> 
The game's assets are compressed into an archive containing a CTC header called "data0.mp3", how did you unpack it?
Here's a BMS script for unpacking assets of this game:
[mp3Unpacker.zip](https://xentaxbackup.github.io/file/17178_mp3Unpacker.zip)
## Post #16
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-11T12:41:46+00:00
- Post Title: Re: 封神召唤师 - God Summoner (*.sm, *.skel, *.anim)

> Reply from einherjar007 ↑Tue Dec 10, 2019 1:35 pm at Tue Dec 10, 2019 1:35 pm
>
> the game of "启源女神" uses the same CTC header data0.mp3.
I don't know how to uncompress CTC header mp3 containers, so I don't know if * .sm, * .skel, * .anim are included.
Here's the BMS script for this game:
[mp3Unpacker_lz4.zip](https://xentaxbackup.github.io/file/17179_mp3Unpacker_lz4.zip)
## Post #17
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-12-18T16:23:01+00:00
- Post Title: Re: 封神召唤师 - God Summoner (*.sm, *.skel, *.anim)

> Reply from Bigchillghost ↑Wed Dec 11, 2019 8:41 pm at Wed Dec 11, 2019 8:41 pm
>
> 
einherjar007 wrote: ↑Tue Dec 10, 2019 1:35 pmthe game of "启源女神" uses the same CTC header data0.mp3.
I don't know how to uncompress CTC header mp3 containers, so I don't know if * .sm, * .skel, * .anim are included.

Here's the BMS script for this game:

Mate, I don't know how to contact you, can you look at this thread that I made, no one repiled it for days  
[viewtopic.php?f=10&t=21497](https://forum.xentax.com/viewtopic.php?f=10&t=21497)
