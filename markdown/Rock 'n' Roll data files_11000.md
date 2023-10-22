## Post #1
- Username: kaydash
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Nov 27, 2013 4:15 pm
- Post datetime: 2013-11-27T14:33:08+00:00
- Post Title: Rock 'n' Roll data files

Hello!

(First post and I'm pretty happy to have found a game research forum!)

As a kid I played Rainbow Arts' [Rock 'n' Roll](https://en.wikipedia.org/wiki/Rock_%27n%27_Roll_%28video_game%29) (for PC) and loved it, I found myself wishing that I could make my own levels for the game and perhaps even a modern clone (that would allow you to import the original data files.)

I spent quite a bit of time staring at the data files in a hex editor and managed to guess my way to a very basic understanding of their structure; although not really enough to do anything useful with. I also tried unpacking and disassembling the executable, but limited assembly knowledge and a lack of understanding of the concepts employed in writing 16-bit games for hardware far more limited than today's meant that the code was incredibly hard for me to follow and understand.

Has anyone ever attempted to make sense of this data or have a good understanding of how 16-bit games for DOS would have been written and have experience disassembling 16-bit DOS software?

Unfortunately I'm not aware of any demo for the game, but some [creative Googling](https://www.google.com/search?q=lock+n+loll+abandonware) could be of some help.
## Post #2
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-11-27T21:11:17+00:00
- Post Title: Rock 'n' Roll data files

I'm not sure if I'll be able to help but happy to have a quick look if you have a unprotected copy of the exe you could send? Seems all the copies I find have some sort of compression/copy protection.
## Post #3
- Username: kaydash
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Nov 27, 2013 4:15 pm
- Post datetime: 2013-11-27T22:27:55+00:00
- Post Title: Rock 'n' Roll data files

> Reply from twisted
>
> I'm not sure if I'll be able to help but happy to have a quick look if you have a unprotected copy of the exe you could send? Seems all the copies I find have some sort of compression/copy protection.

I'm not sure exactly how it's packed but UPX managed to unpack it.
## Post #4
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-11-28T13:07:03+00:00
- Post Title: Rock 'n' Roll data files

Are you sure? UPX didn't work for me and considering UPX wasn't developed until 1996 and this game is from 89 i'm not surprised!
## Post #5
- Username: kaydash
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Nov 27, 2013 4:15 pm
- Post datetime: 2013-11-28T23:17:54+00:00
- Post Title: Rock 'n' Roll data files

> Reply from twisted
>
> Are you sure? UPX didn't work for me and considering UPX wasn't developed until 1996 and this game is from 89 i'm not surprised!

It's been a while since I performed all this dark magic, so perhaps I'm misremembering. UPX could still support whatever packing method was used.

Here's the unpacked executable though: [http://cl.ly/3w2n0G0p291i/urock.exe](http://cl.ly/3w2n0G0p291i/urock.exe)
## Post #6
- Username: kaydash
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Nov 27, 2013 4:15 pm
- Post datetime: 2013-11-28T23:23:34+00:00
- Post Title: Rock 'n' Roll data files

> Reply from kaydash
>
> It's been a while since I performed all this dark magic, so perhaps I'm misremembering. UPX could still support whatever packing method was used.
I guess I misremembered, sorry about the confusion:

```
ROCKROLL.EXE: MS-DOS executable, MZ for MS-DOS, LZEXE v0.91 compressed
```
## Post #7
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2013-11-29T10:52:27+00:00
- Post Title: Rock 'n' Roll data files

You could try unlzexe from [here](http://www.exetools.com/unpackers.htm)

oh and by the way, it is really great to see someone tackling such an old game, I fondly remember playing this on my Amiga for hours and hours... Great little game although I never managed to finish it (I still remember how the cheat system works, with the code you have to enter to select the starting level)
## Post #8
- Username: kaydash
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Nov 27, 2013 4:15 pm
- Post datetime: 2013-11-29T13:37:36+00:00
- Post Title: Rock 'n' Roll data files

> Reply from Darkstar
>
> You could try unlzexe from here
The author [still hosts LZEXE](http://bellard.org/lzexe.html), which comes with an unpacker.

> Reply from Darkstar
>
> oh and by the way, it is really great to see someone tackling such an old game, I fondly remember playing this on my Amiga for hours and hours... Great little game although I never managed to finish it (I still remember how the cheat system works, with the code you have to enter to select the starting level)
Haha, I never managed to finish it either, some of the time limited levels (that occurred right before you were given a save code) were incredibly tough.

I found an [old IDA database](http://cl.ly/1N1P0e0U1R04/urock.idb) and [some code](http://cl.ly/2z3I1L0p473h/rockroll_code.zip) I wrote to test some of my guesses. (Treat anything here as an assumption, basically.)

Unfortunately I think over the years I've managed to lose and rewrite these things several times and I suspect that these are not actually my most recent attempts, but if they help anyone get more than nothing done then I guess they weren't completely useless.
