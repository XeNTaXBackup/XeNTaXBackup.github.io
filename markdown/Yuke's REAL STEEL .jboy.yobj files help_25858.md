## Post #1
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2022-09-28T21:58:21+00:00
- Post Title: Yuke's REAL STEEL .jboy/.yobj files help

i need some help extracting the .jboy/yobj format models from REAL STEEL THE VIDEO GAME i had previously asked im for this format from the same engine
for the game pacific rim the video game from (ps3) but the noesis plugin that Durik256 doesn't work in that game, can't someone help ?  



Samples
Char and Stages:[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/111goWYzvRrGeSBHBUqQAqnKny90mJpUH?usp=sharing)

Pacific Rim jboy plugin noesis(maybe it's useful):[viewtopic.php?f=16&t=25367#p184641](https://forum.xentax.com/viewtopic.php?f=16&t=25367#p184641)


Info:I don't know much about formats and programming but if anyone can make a plugin I would appreciate it
## Post #2
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2022-10-02T06:50:53+00:00
- Post Title: Yuke's REAL STEEL .jboy/.yobj files help

I had forgotten to mention the textures are usually at 000A.dat and 000C.dat
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-02T08:47:53+00:00
- Post Title: Yuke's REAL STEEL .jboy/.yobj files help

0-jbopy.jpg (166.7 KiB) Viewed 212 times

(face index count: estimated value only)
## Post #4
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2022-10-04T19:51:06+00:00
- Post Title: Yuke's REAL STEEL .jboy/.yobj files help

> Reply from shakotay2 ↑Sun Oct 02, 2022 4:47 pm at Sun Oct 02, 2022 4:47 pm
>
> 
0-jbopy.jpg(face index count: estimated value only)

was this supposed to be normal?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-04T20:08:37+00:00
- Post Title: Yuke's REAL STEEL .jboy/.yobj files help

Without giving the params you used no one can tell.
## Post #6
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2022-10-04T20:24:04+00:00
- Post Title: Yuke's REAL STEEL .jboy/.yobj files help

> Reply from shakotay2 ↑Wed Oct 05, 2022 4:08 am at Wed Oct 05, 2022 4:08 am
>
> 
Without giving the params you used no one can tell.

literally the same as yours

I'm trying to learn the logic of the tool
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-04T21:15:44+00:00
- Post Title: Yuke's REAL STEEL .jboy/.yobj files help

> Reply from LeoFeroz ↑Wed Oct 05, 2022 4:24 am at Wed Oct 05, 2022 4:24 am
>
> 
shakotay2 wrote: ↑Wed Oct 05, 2022 4:08 am
Without giving the params you used no one can tell.


literally the same as yoursAh, see. The superfluous face is visible after blender import only. Simply delete it...

btw: you may increase the face index count to 29236 (and will still get that one error face, funny).
It's only visible in hex2obj's mesh_viewer uv map when rotating the map.
## Post #8
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2022-10-04T21:48:32+00:00
- Post Title: Yuke's REAL STEEL .jboy/.yobj files help

Do you have any tips for me I'm quite new working with this type of tool, let's just say I'm very layman
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-05T08:05:23+00:00
- Post Title: Yuke's REAL STEEL .jboy/.yobj files help

read the tutorials, see links in my sig.

Apart from using big endian the mesh data of .jboy is simple.
uv start address = vStart + vCount * 52
v= vertices
## Post #10
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-10-07T03:52:07+00:00
- Post Title: Yuke's REAL STEEL .jboy/.yobj files help

> Reply from shakotay2 ↑Wed Oct 05, 2022 5:15 am at Wed Oct 05, 2022 5:15 am
>
> 
The superfluous face is visible after blender import only. Simply delete it...
this is because the index block is divided into two submesh
1)num_indices: 9254 offset: 927256
2)num_indices:19981 offset: 945764

> Reply from LeoFeroz ↑Thu Sep 29, 2022 5:58 am at Thu Sep 29, 2022 5:58 am
>
> 
but the noesis plugin that Durik256 doesn't work in that game, can't someone help ?
who would help me  

edit: add weight, and add plagin fod *.dat(texture)
[fmt_jboy_RS.zip](https://xentaxbackup.github.io/file/22887_fmt_jboy_RS.zip)
## Post #11
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2022-10-08T00:23:04+00:00
- Post Title: Yuke's REAL STEEL .jboy/.yobj files help

> Reply from Durik256 ↑Fri Oct 07, 2022 11:52 am at Fri Oct 07, 2022 11:52 am
>
> 
shakotay2 wrote: ↑Wed Oct 05, 2022 5:15 am
The superfluous face is visible after blender import only. Simply delete it...

this is because the index block is divided into two submesh
1)num_indices: 9254 offset: 927256
2)num_indices:19981 offset: 945764
LeoFeroz wrote: ↑Thu Sep 29, 2022 5:58 am
but the noesis plugin that Durik256 doesn't work in that game, can't someone help ? 

who would help me

Durik I love you   

there is only one suggestion rename the plugin to avoid conflict and create a new post to put the fmt jboy plugins for pacific rim and fmt jboy for real steel

dude thank you so much

I know it's something very complex but if you can make the weights work I would also appreciate it
## Post #12
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-10-08T03:57:04+00:00
- Post Title: Yuke's REAL STEEL .jboy/.yobj files help

> Reply from LeoFeroz ↑Sat Oct 08, 2022 8:23 am at Sat Oct 08, 2022 8:23 am
>
> 
weights work
i update plugin (click on arrow)

> Reply from Durik256 ↑Fri Oct 07, 2022 11:52 am at Fri Oct 07, 2022 11:52 am
>
> 
plugin
## Post #13
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2022-10-08T06:00:33+00:00
- Post Title: Yuke's REAL STEEL .jboy/.yobj files help

> Reply from Durik256 ↑Fri Oct 07, 2022 11:52 am at Fri Oct 07, 2022 11:52 am
>
> 
plugin

Man I realized that there is something wrong with the bones in general now with the weights it looks like they are a little lower it doesn't seem to be correct

Extracted



Manually fixed


this is valid for all bones but basically one of the axes is always in the wrong position
