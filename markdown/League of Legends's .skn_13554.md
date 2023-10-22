## Post #1
- Username: VoliPanda
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Sep 07, 2015 4:49 am
- Post datetime: 2015-11-21T04:08:31+00:00
- Post Title: League of Legends's .skn

Greetings everyone!

I'm having issues with the LoL .skn files. So, before any question, here's my set:
1- Noesis w/ finale00's plugin.
1.1- finale00's plugin was encountering an error while trying to start Noesis, so I did one change which is detailed in the following topic, by Shakotay2:
[viewtopic.php?f=16&t=8630&hilit=league+of+legends](http://forum.xentax.com/viewtopic.php?f=16&t=8630&hilit=league+of+legends) and it stopped having the startup issue. It also recongnizes .skn and .skl files, but whenever I try to open any .skn files, I get this error


My guess is that my plugin is working but not updated? Which is why it says that it has failed to load/construct model? I have little no none experience in programming with Java and C++ but never actually studied python...
and also this is so far, the best method I've found to read, open and convert these .skn files. I've been trying hard on SIU with Riot File Translator's Maya plugin and skntoobj but also no success.
Can anyone help me? I wanted to know how will I be able to get the newer 3D models such as Dragon Trainer Tristana and Braum Lionheart?
Thanks in advance!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-23T20:44:49+00:00
- Post Title: League of Legends's .skn

> Reply from VoliPanda
>
> Which is why it says that it has failed to load/construct model?upload such a model (or pm a link) then may be I can tell more

edit: thx - works for me (Noesis 4.12):



Tristana.JPG (98.39 KiB) Viewed 175 times
## Post #3
- Username: VoliPanda
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Sep 07, 2015 4:49 am
- Post datetime: 2015-11-23T21:01:22+00:00
- Post Title: League of Legends's .skn

Just verified my plugin code...It's exactly the same you posted D:
Guess .skn files doesn't like me haha.
## Post #4
- Username: VoliPanda
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Sep 07, 2015 4:49 am
- Post datetime: 2015-11-23T21:06:26+00:00
- Post Title: League of Legends's .skn

Here says that the problem is encountered at line 25, which has the following:
mdl  = rapi.rpgConstructModel()

Would you mind sending me your code? Just wanted to compare and check why this is happening
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-23T21:13:38+00:00
- Post Title: League of Legends's .skn

PMed you.

It's not my code, it's finale00's iirc.
I made the patch only.
## Post #6
- Username: VoliPanda
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Sep 07, 2015 4:49 am
- Post datetime: 2015-11-23T21:30:03+00:00
- Post Title: League of Legends's .skn

yeah, I know that. I meant the one you have/patched haha
Finally...It's working now. Thanks a lot. I'll try and figure it out why the other one wasn't working
## Post #7
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-11-23T22:20:20+00:00
- Post Title: League of Legends's .skn

Could you send me a link to the extracted skn and skl? I'd like to try something out.
## Post #8
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2015-11-28T21:41:33+00:00
- Post Title: League of Legends's .skn

[http://cr1t3r10n.deviantart.com/gallery ... Of-Legends](http://cr1t3r10n.deviantart.com/gallery/56951466/League-Of-Legends)
