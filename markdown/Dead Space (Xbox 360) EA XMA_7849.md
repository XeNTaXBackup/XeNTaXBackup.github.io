## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2011-12-12T20:34:05+00:00
- Post Title: Dead Space (Xbox 360) EA XMA

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-12-12T22:48:28+00:00
- Post Title: Dead Space (Xbox 360) EA XMA

Cut off 20 bytes. Then run though ea multi xma.
## Post #3
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-12-13T09:42:35+00:00
- Post Title: Dead Space (Xbox 360) EA XMA

fwiw you don't need to cut anything, ea_multi_xma takes an optional offset argument:
```
ea_multi_xma aud_se_5_9_hunter.exa.snu -o 20
```

That 20 is hexadecimal, by the way.
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2011-12-13T15:14:48+00:00
- Post Title: Dead Space (Xbox 360) EA XMA

Argh, no wonder it didn't work! I only tried with "0x20"!
Thanks for clearing that up.
## Post #5
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-12-14T08:54:34+00:00
- Post Title: Dead Space (Xbox 360) EA XMA

Sorry about that, not sure wtf I was thinking.
