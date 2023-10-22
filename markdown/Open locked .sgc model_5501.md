## Post #1
- Username: x0a
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 08, 2010 12:40 am
- Post datetime: 2010-12-06T00:06:15+00:00
- Post Title: Open locked .sgc model

Hello,

is it somehow possible to open a locked .sgc model file (from Richard burns rallye)?

Maybe edit with a hex editor?

Thank you
## Post #2
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-12-06T09:53:59+00:00
- Post Title: Open locked .sgc model

Did you try the 3D Object Converter ?

[http://web.t-online.hu/karpo](http://web.t-online.hu/karpo)
## Post #3
- Username: x0a
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 08, 2010 12:40 am
- Post datetime: 2010-12-06T10:57:17+00:00
- Post Title: Open locked .sgc model

Yes, I've tried it. It opens up the model, it is a bit messed up and many polygons are bad. When I save the model with another filetype and reopen the model with the software I use there is nothing.
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-12-06T14:25:42+00:00
- Post Title: Open locked .sgc model

I tested my .sgc loader module with several sample files I did find on the Net.
[http://www.bhmotorsports.com/RBR/downloads/4053](http://www.bhmotorsports.com/RBR/downloads/4053)

Unfortunately some of .sgc files don't have a parent object referenced from the subobjects. I don't know how can I move the 'flying' parts to the correct 'place' automatically.
## Post #5
- Username: x0a
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 08, 2010 12:40 am
- Post datetime: 2010-12-07T13:39:54+00:00
- Post Title: Open locked .sgc model

Hey, I managed to open a locked .sgc model with the 3dobject converter, also the textures are right.

But there is stil a problem: When I save the model ex. as a Waveobject .obj file, and reopen the model with another software (3dsimed), the textures don't match themodel anymore. Why?
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-12-07T16:04:47+00:00
- Post Title: Open locked .sgc model

I don't have your modeler prg, but maybe it flips the UV datas from the .obj file.

I think you must use the Tools/Flip UV Map Vertically function (or press the CTRL+U buttons) after .sgc load (before .obj export).
## Post #7
- Username: x0a
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 08, 2010 12:40 am
- Post datetime: 2010-12-07T17:15:19+00:00
- Post Title: Open locked .sgc model

I think there must be another problem. Here are two screens from what I mean. It seems the texture is not frong mapped but something other is messed up.
[1.jpg](https://xentaxbackup.github.io/file/3668_1.jpg)
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-12-07T20:55:46+00:00
- Post Title: Open locked .sgc model

My Wavefront .obj/mtl exporter module works fine, you can check it out using other programs like Deep Exploration, 3D Studio Max, Maya, Softimage...
## Post #9
- Username: x0a
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 08, 2010 12:40 am
- Post datetime: 2011-02-13T18:18:09+00:00
- Post Title: Open locked .sgc model

> Reply from Karpati
>
> 
Unfortunately some of .sgc files don't have a parent object referenced from the subobjects. I don't know how can I move the 'flying' parts to the correct 'place' automatically.

Somebody solved this problem?
## Post #10
- Username: x0a
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 08, 2010 12:40 am
- Post datetime: 2011-02-15T11:45:15+00:00
- Post Title: Open locked .sgc model

Here is a screenshot for better immagination:
[zuz.jpg](https://xentaxbackup.github.io/file/3923_zuz.jpg)
## Post #11
- Username: x0a
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 08, 2010 12:40 am
- Post datetime: 2011-02-24T09:52:03+00:00
- Post Title: Open locked .sgc model

No solution for this?
## Post #12
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-10-06T18:30:49+00:00
- Post Title: Open locked .sgc model

Sorry for the bump, but I am looking for a solution to this too. Is there a free way? I use blender. I don't like 3d object converter.
## Post #13
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-10-06T19:43:37+00:00
- Post Title: Open locked .sgc model

I got it imported in a zmodeler 2 but HOW DO I UNLOCK THE LOCKED ONES???
## Post #14
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-07-20T16:31:12+00:00
- Post Title: Open locked .sgc model

Still no solution
## Post #15
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-07-20T18:45:01+00:00
- Post Title: Open locked .sgc model

> Reply from x0a ↑Thu Feb 24, 2011 5:52 pm at Thu Feb 24, 2011 5:52 pm
>
> 
No solution for this?

Did you try the Configuration/Import/Richard Burns Rally .sgc Skip the hierarchy information parameter (set to true) on your .sgc model?
