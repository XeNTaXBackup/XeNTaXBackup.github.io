## Post #1
- Username: babidy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 10, 2021 8:33 pm
- Post datetime: 2022-01-11T17:11:38+00:00
- Post Title: Model extract need help [done]

When I follow the tutorial it work
I just try to do by myself all day about this


can anybody help how to find where mesh start please
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-11T17:36:41+00:00
- Post Title: Model extract need help [done]

The "start of vertices" you used seems to be correct but well, sadly I don't get familiar with other tools, so here's what I get:
.



smileface-grm.png (107.99 KiB) Viewed 547 times


(Reminds me of a deja vue...)
## Post #3
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-12T02:28:59+00:00
- Post Title: Model extract need help [done]

> Reply from babidy ↑Wed Jan 12, 2022 1:11 am at Wed Jan 12, 2022 1:11 am
>
> 
can anybody help

[fmt_rgm.zip](https://xentaxbackup.github.io/file/21626_fmt_rgm.zip)
## Post #4
- Username: babidy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 10, 2021 8:33 pm
- Post datetime: 2022-01-16T10:28:13+00:00
- Post Title: Model extract need help [done]

@Durik256 thanks for script, some file can load but almost files can't open. and I dont know about the code.

@shakotay2 do you have the easy way how to find the value, I think almost file is the same structure

example file [https://drive.google.com/file/d/1enxoZV ... sp=sharing](https://drive.google.com/file/d/1enxoZVrDp6Zlf_3Z8FrUa4tH93O2iuAV/view?usp=sharing)
thanks in advance
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-16T11:24:26+00:00
- Post Title: Model extract need help [done]

blocks starting with FFFF may lead the way (0000803F to follow; always? dunno):
.



shirt.png (75.41 KiB) Viewed 477 times
## Post #6
- Username: babidy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 10, 2021 8:33 pm
- Post datetime: 2022-01-16T12:05:38+00:00
- Post Title: Model extract need help [done]

@shakotay2 alright I can find start value, and I see step2 is always 32 and 24
but how to know the count value. please don't be annoyed me for noob.

sample
[https://drive.google.com/file/d/18GgsS1 ... sp=sharing](https://drive.google.com/file/d/18GgsS1qdLBDmXGdeDaa9J7LuB-aCsVaa/view?usp=sharing)
[aassdd.png](https://xentaxbackup.github.io/file/21623_aassdd.png)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-16T12:43:55+00:00
- Post Title: Model extract need help [done]

At 0x249 it's FF000000 (intel little endian data notation) -> 0x000000FF, 255 decimal

You'll need to switch from "seq" to "VB", btw.
.



face index count.png (20.47 KiB) Viewed 462 times
## Post #8
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-16T18:35:46+00:00
- Post Title: Model extract need help [done]

> Reply from babidy ↑Sun Jan 16, 2022 6:28 pm at Sun Jan 16, 2022 6:28 pm
>
> 
@Durik256 thanks for script, some file can load but almost files can't open. and I dont know about the code.
as I said: "it's hard to do with one model".
This is because the name of the model is in some strange language. just had to readUbyte() and not a readByte() in method "searchString(bs)".
After the bones come matrices.(in the model that you provided there was one matrix that I skip)

I update plugin:

> Reply from Durik256 ↑Wed Jan 12, 2022 10:28 am at Wed Jan 12, 2022 10:28 am
>
> 

Now opens all models except animation without mesh.
Rename the texture, otherwise dragNdrop won't work!
## Post #9
- Username: babidy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 10, 2021 8:33 pm
- Post datetime: 2022-01-17T03:39:32+00:00
- Post Title: Model extract need help [done]

@Durik256  oh thanks man, now I can view it.

and how you view with texture? need more plugin? or press a shortcut key?
## Post #10
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-17T08:13:07+00:00
- Post Title: Model extract need help [done]

> Reply from babidy ↑Mon Jan 17, 2022 11:39 am at Mon Jan 17, 2022 11:39 am
>
> 
and how you view with texture? need more plugin? or press a shortcut key?

drag and drop texture on noesis preview and click "no"
