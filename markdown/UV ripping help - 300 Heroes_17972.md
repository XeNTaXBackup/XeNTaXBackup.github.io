## Post #1
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2018-04-14T11:25:18+00:00
- Post Title: UV ripping help - 300 Heroes

So far I managed to get the mesh but can never get the UV values.
Anyone available to mind helping me out?

This is the only model I need from the game anyway.



[http://www.mediafire.com/file/n4lypx4i7q9aj6m/](http://www.mediafire.com/file/n4lypx4i7q9aj6m/)

Thank you in advance.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-14T12:00:31+00:00
- Post Title: UV ripping help - 300 Heroes

No prob: 



UV.jpg (91.52 KiB) Viewed 331 times
## Post #3
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2018-04-14T12:07:59+00:00
- Post Title: UV ripping help - 300 Heroes

That was quick, 

thank you very much
## Post #4
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2018-04-14T12:50:15+00:00
- Post Title: UV ripping help - 300 Heroes

Oh sorry, last one

A friend of mine wanted to rip this but he couldn't get the face indices nor the vertex start address for the main model, just the sword.

If anyone wants to do it, thank you. I owe him a favor.

[http://www.mediafire.com/file/bd9r5b5dd4ok6un/](http://www.mediafire.com/file/bd9r5b5dd4ok6un/)
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-14T13:08:05+00:00
- Post Title: UV ripping help - 300 Heroes

> Reply from ailephi
>
> A friend of mine wanted to rip this but he couldn't get the face indices nor the vertex start address for the main model, just the sword.
And how are you doing?

Easy as always:



mdl.jpg (95.94 KiB) Viewed 322 times
## Post #6
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2018-04-14T13:40:17+00:00
- Post Title: UV ripping help - 300 Heroes

I really need to learn more about hex language
thank you again, my dude
## Post #7
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2018-04-14T14:13:58+00:00
- Post Title: UV ripping help - 300 Heroes

btw for getting the UVs, was the process the same for both models?

I want to learn how to get them myself so I can practice on the other models from this game
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-14T14:33:18+00:00
- Post Title: UV ripping help - 300 Heroes

> Reply from ailephi
>
> btw for getting the UVs, was the process the same for both models?
Of course it is. The model is using seq format where data chunks are in the following order:
V coords, NM coords, UV coords, then face indices buffer. 
Didn't find any fields about the counts so I guess you'll have to do it manually. Maybe there're other files that containing the necessary info.
## Post #9
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2018-04-14T14:41:01+00:00
- Post Title: UV ripping help - 300 Heroes

Aye aye, exactly what I needed to know

I should be able to rip them properly now after some time

I owe ya
## Post #10
- Username: LoveLynx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Feb 08, 2018 8:30 am
- Post datetime: 2022-03-02T09:44:45+00:00
- Post Title: UV ripping help - 300 Heroes

Sorry for the Necro, but is it possible someone could rip Sora Kasugano's model from here, or tell me how to rip the models myself? I also would have to know where to get hex2obj, I guess. 
Sorry again.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-03-02T15:56:55+00:00
- Post Title: UV ripping help - 300 Heroes

hex2obj zips are uploaded in three posts starting from here (click up arrow):

> Reply from shakotay2 ↑Sun Mar 07, 2021 10:29 pm at Sun Mar 07, 2021 10:29 pm
>
> 
(All three zips are required.)
## Post #12
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-03T18:35:34+00:00
- Post Title: UV ripping help - 300 Heroes

> Reply from LoveLynx ↑Wed Mar 02, 2022 5:44 pm at Wed Mar 02, 2022 5:44 pm
>
> 
or tell me how to rip the models

i create noesis plugin.
you need only write offset indices, vertex and count.
line 21 inside script as (offset = [[indices_offset, num_indices, vert_offset, num_vert], ...])
submesh can be as many as you want.

example:

```
offset = [[36866, 624, 33104, 114], [202550, 22284, 40850, 4900]]

#for 00002674.dat >> 
offset = [[39291, 996, 31008, 251], [0x3b4b1, 25965, 0xb8cb, 5926]]

```

or post your model...
(where can i download this game?)
[fmt_300_Heroes.zip](https://xentaxbackup.github.io/file/21873_fmt_300_Heroes.zip)
## Post #13
- Username: LoveLynx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Feb 08, 2018 8:30 am
- Post datetime: 2022-03-13T01:54:21+00:00
- Post Title: UV ripping help - 300 Heroes

...I think I'm too stupid for this. XD 

I'm looking for the Sora Kasugano model to get ripped, but idk how to do any of this. 

[https://i.imgur.com/iPmjDmI.mp4](https://i.imgur.com/iPmjDmI.mp4) 

^ That's the video/gif of her model. IDK if she always has her rabbit in her arms either or anything. x.x 

How would I get the Noesis plugin to work? How do I figure out which hex is Sora's? So many questions ;; I'm sorry I'm dumb aaaa
## Post #14
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-13T12:30:28+00:00
- Post Title: UV ripping help - 300 Heroes

> Reply from LoveLynx ↑Sun Mar 13, 2022 9:54 am at Sun Mar 13, 2022 9:54 am
>
> 
I'm looking for the Sora Kasugano model to get ripped
I don't have the game, you need to share the files, or at least a link to the game.  otherwise I won't be able to help you.
## Post #15
- Username: LoveLynx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Feb 08, 2018 8:30 am
- Post datetime: 2022-03-24T09:15:52+00:00
- Post Title: UV ripping help - 300 Heroes

Ohhhhhhhh, I feel dumb. XD 

[http://300.jumpw.com/download.html](http://300.jumpw.com/download.html) 

download From here ; and click the dark blue button!
## Post #16
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-24T11:59:25+00:00
- Post Title: Re: UV ripping help - 300 Heroes

> Reply from LoveLynx ↑Thu Mar 24, 2022 5:15 pm at Thu Mar 24, 2022 5:15 pm
>
> 
download From here ; and click the dark blue button!
to download you need an account (the phone number, chinese as far as I understand)
## Post #17
- Username: xNui
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 05, 2021 2:52 am
- Post datetime: 2022-08-07T22:29:25+00:00
- Post Title: Re: UV ripping help - 300 Heroes

Hey, do you still need? You no longer need an account to download, just downloaded it, the game is 6.5gb but I can upload it to google drive if you wish to! I made a new post as well regarding this game, check my profile, uploaded 1 data file there out of 4 (including a script with outdated decryption offset or something similar, which needs updating)
## Post #18
- Username: Yun666
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 10, 2022 5:07 pm
- Post datetime: 2022-08-09T18:18:55+00:00
- Post Title: Re: UV ripping help - 300 Heroes

据我所知这个300英雄的模型可以直接转换成fbx格式，你们需要一些帮助吗？
