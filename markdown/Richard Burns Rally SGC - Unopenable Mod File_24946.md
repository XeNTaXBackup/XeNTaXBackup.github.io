## Post #1
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2022-01-14T01:37:12+00:00
- Post Title: Richard Burns Rally SGC - Unopenable Mod File?

So I am trying to open this [Fiesta ST](https://rbr.onlineracing.cz/index.php?act=download&cat=1101) for quite some time now.
Yes, I am aware this is a mod. 

It seems I can't open this one specifically for some reason...what gives?

Opening it with ZModeler2 gives me this dreaded "Out of memory" error.


I have plenty of RAM and I have opened many files with DOUBLE the file size of this model before.

Opening it with 3D Object Converter...comes up with this...eek! (Yes I have contacted the author about this, he's unsure on what to do about it Unfortunately this also happens with the stock original cars.)


So is there any way to open this correctly or am I doomed?

(btw is mods files allowed on this forum? sorry if it isn't...  )
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-14T04:35:55+00:00
- Post Title: Richard Burns Rally SGC - Unopenable Mod File?

> Reply from ReVolt ↑Fri Jan 14, 2022 9:37 am at Fri Jan 14, 2022 9:37 am
>
> Opening it with 3D Object Converter...comes up with this...eek! (Yes I have contacted the author about this, he's unsure on what to do about itAnd you expect US to solve the problem?  Funny.  
.



fiestast-sgc.png (143.59 KiB) Viewed 76 times

Floating parts probably need matrix multiplying. In simpler cases it's just offset positions to find. Good luck! 

You could move the hood manually then try to find the resulting position in the SGC data. (Worked on another format for me.)
upps, 175 submeshes??
## Post #3
- Username: Fengo
- Rank: beginner
- Number of posts: 24
- Joined date: Fri Aug 12, 2011 3:02 pm
- Post datetime: 2022-01-14T07:14:26+00:00
- Post Title: Richard Burns Rally SGC - Unopenable Mod File?

Did you ask the original author? They probably locked the file so it can't be imported.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-14T21:50:19+00:00
- Post Title: Richard Burns Rally SGC - Unopenable Mod File?

> Reply from ReVolt ↑Fri Jan 14, 2022 9:37 am at Fri Jan 14, 2022 9:37 am
>
> Opening it with 3D Object Converter...comes up with this...eek! (Yes I have contacted the author about this, he's unsure on what to do about it Unfortunately this also happens with the stock original cars.)Guess, he uses the position offsets (if any), but maybe it doesn't work for some models.

I made a Make_H2O project (for testing only, no uvs) and it looks like so (maybe some lods missing):
.



fiesta_st.png (94.76 KiB) Viewed 54 times
