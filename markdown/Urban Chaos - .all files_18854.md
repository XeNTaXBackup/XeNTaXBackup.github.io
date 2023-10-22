## Post #1
- Username: Gruni
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 26, 2018 6:48 am
- Post datetime: 2018-09-24T16:14:56+00:00
- Post Title: Urban Chaos - .all files?

I am currently playing around with the Source Code for Urban Chaos and I can't get my head around those .all files. Since .all is a super stupid file ending that makes it almost impossible to find anything about it via google, I was wondering if anyone has made some experience or progression with opening / exporting / importing character models from MuckyFoot's Urban Chaos.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2018-09-24T19:47:18+00:00
- Post Title: Urban Chaos - .all files?

As far as I know, ".all" files contain animations, so you should start looking for answers in file MuckyFoot-UrbanChaos-master\fallen\Source\Anim.cpp
Take a look at function "load_anim_system" and others in this file.
## Post #3
- Username: Gruni
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 26, 2018 6:48 am
- Post datetime: 2018-09-24T20:19:49+00:00
- Post Title: Urban Chaos - .all files?

According to io.cpp .all-Files seem to be "multi-prims". Currently trying to figure out how to properly split the data.

Thanks for the hint, so far.
