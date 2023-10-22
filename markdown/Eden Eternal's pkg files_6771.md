## Post #1
- Username: Castiel
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 13, 2011 5:09 am
- Post datetime: 2011-06-12T21:50:49+00:00
- Post Title: Eden Eternal's pkg files

I'm trying to extract the archive and I'm stuck. I read [this](http://wiki.xentax.com/index.php/DGTEFF) and tried my hand at it but I get a zlib unknown compression error at some (a lot?) of the files. I've already managed to extract quite a bit of the files, and did run offzip once before.

[pkg.idx](http://www.sendspace.com/file/ckz2ti)

In the idx, you have I think 16302 files in total. I only got about 15100. [Here's](http://www.sendspace.com/file/eorhkq) what I'm running.

Anyway, here's the error. Position is 6527092 in pkg.idx.

```
  Message=Bad state (unknown compression method (0xF7))
  Source=Ionic.Zlib
  StackTrace:
       at Ionic.Zlib.InflateManager.Inflate(FlushType flush)
       [snip]

```


There are a whole lot of fields I just ignored, and there's one right in between the offset and the packed file size, 4 bytes, that I think may actually do something important.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-13T00:20:10+00:00
- Post Title: Eden Eternal's pkg files

maybe the following script for quickbms could help you:
[http://aluigi.org/papers/bms/aeriagames.bms](http://aluigi.org/papers/bms/aeriagames.bms)
## Post #3
- Username: Castiel
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 13, 2011 5:09 am
- Post datetime: 2011-06-13T01:25:29+00:00
- Post Title: Eden Eternal's pkg files

> Reply from aluigi
>
> maybe the following script for quickbms could help you:
http://aluigi.org/papers/bms/aeriagames.bms

Wow, I see what I did wrong. I was doing directory -> file, but it's file -> directory. Thanks!
