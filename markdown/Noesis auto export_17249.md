## Post #1
- Username: DGIorio
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 11, 2016 6:12 am
- Post datetime: 2017-11-05T04:59:57+00:00
- Post Title: Noesis: auto export?

Hello guys,

I've been working on a plugin for noesis to import Burnout Paradise city models (TRK_UNITs), but I have problems when importing the files, because of some memory limitations in Noesis (32 bits program). What I'm doing to solve it is opening 20 models by time, so I export this one, edit the script and open the next 20 models, and so on. What could I do to bypass this memory problem? Because the people who are using my plugin are getting difficulties doing the process.

I had the idea of auto exporting the models to .obj or .dae (if possible merging them in the same output file), but I don't know how to make it or if it's possible.

Thanks in advance!
[fmt_BurnoutParadise_PC_Models.rar](https://xentaxbackup.github.io/file/13523_fmt_BurnoutParadise_PC_Models.rar)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-11-05T11:48:40+00:00
- Post Title: Noesis: auto export?

Noesis has a batch function why do you need to open 20 models at one time?
## Post #3
- Username: DGIorio
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 11, 2016 6:12 am
- Post datetime: 2017-11-05T14:26:45+00:00
- Post Title: Noesis: auto export?

> Reply from chrrox
>
> Noesis has a batch function why do you need to open 20 models at one time?

Hi chrrox 

In Burnout Paradise each track unit has about 100 track pieces (buildings, signs, roads, jumps,...). I already can open them individually, but by this way the track pieces aren't positioned in the map. So I made a script to open the main file inside the TRK_UNIT (InstanceList, each track unit has one of this file), by this way I can open the "whole" track unit, scale and positioned each track piece. The problem is that there are many models to read, scale and positionate and it makes Noesis crash, because of a 32-bits software limitation, so I need to open about 20 models per time to avoid this problem. I would like to bypass this problem, maybe by auto-exporting.

Using the batch function also didn't work, I thought it will work better since there aren't a preview. But thanks anyway.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-11-05T14:50:00+00:00
- Post Title: Noesis: auto export?

32 bit limit is 4gb it seems odd that you would hit that limit loading one race course.
I have loaded hundreds of objects in noesis without problem in my scripts before.
## Post #5
- Username: DGIorio
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 11, 2016 6:12 am
- Post datetime: 2017-11-05T16:31:48+00:00
- Post Title: Noesis: auto export?

> Reply from chrrox
>
> 32 bit limit is 4gb it seems odd that you would hit that limit loading one race course.
I have loaded hundreds of objects in noesis without problem in my scripts before.

Oh I managed to solve the issue, I needed to add "rapi.rpgReset()" in some parts of the script.
Another question, before exporting a model I need do press F2 (Cycle sub-models) until all sub-models be selected (like 300/300), do you know how can I do it automatically by the script? Because when I use batch process it's a problem, because just the first model is exported.
