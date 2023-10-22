## Post #1
- Username: burom
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 22, 2017 2:51 am
- Post datetime: 2017-04-21T19:07:29+00:00
- Post Title: Target Terror (Wii) .bikswap?

I extracted the files for this game, and I'm looking for the animations in particular. Some animations are in /avi/BigActors in .bik format, while others are in /avi in ".bikswap" format. These files aren't playable in RAD tools, and the file header is "iKIB" as opposed to "BIKi" for the regular .bik files. Anyone here have an idea?

Examples: [https://mega.nz/#F!LZkRHJzR!bBoT6JGsPkzleRFMHWmPfw](https://mega.nz/#F!LZkRHJzR!bBoT6JGsPkzleRFMHWmPfw)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-21T19:19:05+00:00
- Post Title: Target Terror (Wii) .bikswap?

the *.bikswap files just use big endian byte order, swap the bytes to little endian and remove the "swap" from the extension and it will play normally in Rad video tools.
## Post #3
- Username: burom
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 22, 2017 2:51 am
- Post datetime: 2017-04-22T02:11:28+00:00
- Post Title: Target Terror (Wii) .bikswap?

Thank you, it worked completely. Swapping the endian-ness of each byte produces valid .bik files.
## Post #4
- Username: Yohan Mollo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 21, 2017 4:41 pm
- Post datetime: 2017-09-21T08:43:07+00:00
- Post Title: Target Terror (Wii) .bikswap?

Thanks! Worked like a charm.
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2017-09-21T09:41:47+00:00
- Post Title: Target Terror (Wii) .bikswap?

> Reply from AceWell
>
> the *.bikswap files just use big endian byte order, swap the bytes to little endian and remove the "swap" from the extension and it will play normally in Rad video tools.

Best twist ever.
