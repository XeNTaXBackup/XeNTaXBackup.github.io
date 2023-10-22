## Post #1
- Username: ValorODST
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 27, 2020 1:06 pm
- Post datetime: 2022-11-02T10:07:57+00:00
- Post Title: Armored Core V - .tpf

Howdy!

Currently looking to convert Armored Core V .TPF files into a usable format like .DDS. They're similar to other From Software titles but none of the converters that are available (Dark Souls, Demon Souls, Elden Ring etc.) do not work with ACV (I'm assuming it's because it's a much older title).

I've attached some samples of various sizes into the dropbox below. If anyone could give me pointers or directions, I would greatly appreciate it.

[https://www.dropbox.com/sh/80liehyvj5xb ... 2NbRa?dl=0](https://www.dropbox.com/sh/80liehyvj5xblxg/AACpKqv5Y5jSelIOTzhq2NbRa?dl=0)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-02T23:15:18+00:00
- Post Title: Armored Core V - .tpf

File format of included TPF files seems to be very similar to format from other From Software games
[http://wiki.xentax.com/index.php/From_Software_TPF](http://wiki.xentax.com/index.php/From_Software_TPF)

But the image data is encrypted (or I just couldn't decode it properly in Noesis :p)
## Post #3
- Username: ValorODST
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 27, 2020 1:06 pm
- Post datetime: 2022-11-02T23:49:38+00:00
- Post Title: Armored Core V - .tpf

Hmm, I'm not sure if they're encrypted. Gh0stBlade's script ([viewtopic.php?t=11844](https://forum.xentax.com/viewtopic.php?t=11844)) for Noesis can produce an "image" while looking at these files, but they aren't being decoded quite correctly.

I'm unfortunately not tech savvy enough to play with it, but I imagine this is pretty close to the result I'm looking for.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-03T00:18:28+00:00
- Post Title: Armored Core V - .tpf

All I can see in Noesis is garbage [https://imgur.com/a/FEM21Gv](https://imgur.com/a/FEM21Gv)
I've also tried some other image types (BC4, BC6, BC7, RGBA, swizzling etc.), but I can always only see garbage.

I'm also getting a lot of errors in Noesis, but it's probably because differences in the file format.

Please share a screenshot here if you can see something else in those samples.
## Post #5
- Username: ValorODST
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 27, 2020 1:06 pm
- Post datetime: 2022-11-03T01:07:57+00:00
- Post Title: Armored Core V - .tpf

Hmm. I'll continue doing research, but otherwise I can grab what I need through a debugger if necessary. Thank you for the effort.
## Post #6
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-11-03T02:45:00+00:00
- Post Title: Armored Core V - .tpf

I guess those samples are from Xbox360 version. The attached script should work for provided samples, it's modified version of the mentioned Gh0stBlade's script.



 fmt_ACV_TPF_xbox360.zip
(905 Bytes) Downloaded 26 times
## Post #7
- Username: ValorODST
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 27, 2020 1:06 pm
- Post datetime: 2022-11-03T02:55:50+00:00
- Post Title: Armored Core V - .tpf

> Reply from Spiritovod ↑Thu Nov 03, 2022 10:45 am at Thu Nov 03, 2022 10:45 am
>
> 
I guess those samples are from Xbox360 version. The attached script should work for provided samples, it's modified version of the mentioned Gh0stBlade's script.


fmt_ACV_TPF_xbox360.zip

Works perfectly! You're the best, thank you!
