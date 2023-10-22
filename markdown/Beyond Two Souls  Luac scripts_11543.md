## Post #1
- Username: HugoPeters
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-26T17:52:19+00:00
- Post Title: Beyond: Two Souls | Luac scripts

As you may or may not know I've been reversing quite a lot of Beyond: Two Souls' structure. I understand how the game works for around 60% - 70%, but one major part that
is stopping me from reversing everything are the precompiled Lua scripts. They're scattered throughout the entire game and take care of almost -everything- besides the splash loading screen.

Here's a small demo of what I can do right now: [https://www.youtube.com/watch?v=D59SAbFSIoU](https://www.youtube.com/watch?v=D59SAbFSIoU)

The scripts still contain all variable names and such, so once they are decompiled further reversing of the game should go pretty smoothly.

I'm not sure if I'm allowed to post direct links to sample files here, so I won't do that, but if you want a few sample files please send me a PM.

Here is a screenshot of the format:



It begins with 0x1b and then "Lua" and 0x51. This is the standard Luac header. The whole thing looks pretty standard to me but LuaDec throws vague errors on it and my own decompiler outputs bogus, so I'm not sure what's going on here. The format is in Big Endian.

I would be very grateful if anyone wants to try to get this working 
As a sidenote, I also have Elf assembly that I'd love to see decompiled 

Thanks in advance,

Hugo
## Post #2
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2014-05-26T18:17:06+00:00
- Post Title: Beyond: Two Souls | Luac scripts

Did you try deleting everything up to .LuaQ and then running luadec on it? Do you mind sending me a sample.
## Post #3
- Username: HugoPeters
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-26T21:07:46+00:00
- Post Title: Beyond: Two Souls | Luac scripts

> Reply from JayK
>
> Did you try deleting everything up to .LuaQ and then running luadec on it? Do you mind sending me a sample.
Yes, that was the first thing I tried.
First LuaDec throws an error about an incorrect header. When changing some value in the header (can't remember which) the error changes to something about an incorrect constant.

I sent you some samples!
## Post #4
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2014-05-26T21:59:46+00:00
- Post Title: Beyond: Two Souls | Luac scripts

Thanks for the samples, using unluac I can get an output. The size of the lua file is the long behind the .LuaQ magic. Save it as its own file and run unluac on it. Not sure how accurate the output is, but it looks as it should be.
## Post #5
- Username: HugoPeters
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-26T22:27:35+00:00
- Post Title: Beyond: Two Souls | Luac scripts

> Reply from JayK
>
> Thanks for the samples, using unluac I can get an output. The size of the lua file is the long behind the .LuaQ magic. Save it as its own file and run unluac on it. Not sure how accurate the output is, but it looks as it should be.
That's fucking awesome! Thanks!!
I did try unluac, but I couldn't get the jar to work. Guess I'll be giving that another go then!!
