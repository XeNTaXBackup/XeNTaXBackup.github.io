## Post #1
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-08-20T20:41:23+00:00
- Post Title: Dissidia NT g1l BGM

I search around and it looks its not easy to convert that format. As I read here:

[https://github.com/losnoco/vgmstream/issues/259](https://github.com/losnoco/vgmstream/issues/259)

They may be a way, but, sadly, I don't know to extract a header or whatever the process involve it should done.
Less if the process should be done on HxD or just simple Notepad++.


If anyone can give me some guidance on how or what I should do, will be appreciate.

PS: on the link they're files as example
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-08-20T21:15:57+00:00
- Post Title: Dissidia NT g1l BGM

Those files have a 28-byte header and then a RIFF/WAVE file.  Those 3 files all contain 1 audio file.

You can use the Simple Cutter feature of VGMToolbox to cut the first 28 bytes, rename the files as *.at9 and they will play in Foobar with the vgmstream plugin.
## Post #3
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-08-23T04:13:56+00:00
- Post Title: Dissidia NT g1l BGM

> Reply from DKDave ↑Wed Aug 21, 2019 5:15 am at Wed Aug 21, 2019 5:15 am
>
> 
Those files have a 28-byte header and then a RIFF/WAVE file.  Those 3 files all contain 1 audio file.

You can use the Simple Cutter feature of VGMToolbox to cut the first 28 bytes, rename the files as *.at9 and they will play in Foobar with the vgmstream plugin.

Thanks! Yet... I give a try and that tool its very out of my league.
But, its good to know they is an alternative for get the BGM data of that game too
