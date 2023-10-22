## Post #1
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-05-18T06:19:59+00:00
- Post Title: What does...

What does "run time error "7": Out Of Memory" mean in mexbinder plus?

Every time I try to open the mrf file in config directory I get that error.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-18T07:06:43+00:00
- Post Title: What does...

This is because you are using an older version of MexBinder on a new type MC.MRF file. MexBinder is not forward compatible. I have yet to release a MexBinder that will use the new type MRF files. 

Different projects take up my time at the moment. But the release of the new Mexbinder is still on the todo list.
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-05-19T00:36:18+00:00
- Post Title: What does...

I'm just curious, whilst the current Mexbinder isn't forward-compatible (how could it be?), will the new MexBinder be backwards-compatible?
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-19T07:01:13+00:00
- Post Title: What does...

> Reply from Dinoguy1000
>
> I'm just curious, whilst the current Mexbinder isn't forward-compatible (how could it be?), will the new MexBinder be backwards-compatible?

Yes. 

And forward-compatibility is possible through header structures that enable a program to distinguish a variable from another and knows which ones it needs. As long as the archive is constructed in a way that enables a "lesser" program to access it (in effect, is backwards compatible) it'll be okay.  Semantics.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-05-19T22:13:55+00:00
- Post Title: What does...

Ahh, I see. Way-over-my-head stuff.
