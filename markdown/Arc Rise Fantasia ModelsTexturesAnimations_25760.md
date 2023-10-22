## Post #1
- Username: spamzilla
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Sep 01, 2022 4:03 am
- Post datetime: 2022-08-31T22:44:42+00:00
- Post Title: Arc Rise Fantasia Models/Textures/Animations

I've been trying to understand how to get the models, textures, and animations from Arc Rise Fantasia and I've made no progress for hours. The point of this thread is for me to understand this. I've tried program after program for nothing. All I need is to get some models into Blender or BRRES viewer.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-01T10:32:35+00:00
- Post Title: Arc Rise Fantasia Models/Textures/Animations

Without a model sample nothing will happen---
## Post #3
- Username: spamzilla
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Sep 01, 2022 4:03 am
- Post datetime: 2022-09-01T15:18:41+00:00
- Post Title: Arc Rise Fantasia Models/Textures/Animations

What is a model sample??
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-01T18:08:30+00:00
- Post Title: Arc Rise Fantasia Models/Textures/Animations

> Reply from spamzilla ↑Thu Sep 01, 2022 11:18 pm at Thu Sep 01, 2022 11:18 pm
>
> 
What is a model sample??Hahaha, good one. What's a model sample? That's a model asset which contains the vertices and faces (at least) of a 3D model as binary data.
There's should be a bres (or BRES) signature/texture string in those WII 3D samples (it's a WII game, isn't it?).

Usually the model files are packed in a (mostly compressed) archive, though.
## Post #5
- Username: spamzilla
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Sep 01, 2022 4:03 am
- Post datetime: 2022-09-01T20:08:01+00:00
- Post Title: Arc Rise Fantasia Models/Textures/Animations

I'm assuming most such models are contained in this game's btl_enemy.vld file. A quick check in the hex editor shows no such BRES entries though.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-02T09:10:36+00:00
- Post Title: Arc Rise Fantasia Models/Textures/Animations

btw, where did you get the info from that it's BRRES format?
## Post #7
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2022-09-02T11:21:05+00:00
- Post Title: Arc Rise Fantasia Models/Textures/Animations

butting in, seems like there's some juicy infos here?
[viewtopic.php?t=7875](https://forum.xentax.com/viewtopic.php?t=7875)
## Post #8
- Username: spamzilla
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Sep 01, 2022 4:03 am
- Post datetime: 2022-09-05T00:35:34+00:00
- Post Title: Arc Rise Fantasia Models/Textures/Animations

When I understood the format of the btl_enemy.vld file I knew writing a program to automate the process would be less vexing than sitting on the hex editor all day. So I came up with this tool instead! It is my first attempt at coding in C# too!
[ARF Model Splitter.7z](https://xentaxbackup.github.io/file/22761_ARF Model Splitter.7z)
