## Post #1
- Username: Edness
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 11, 2018 7:26 pm
- Post datetime: 2019-09-29T19:24:53+00:00
- Post Title: The Sims 2 PS2 3D Models

I've been working on a project related to The Sims 2 for the PS2 for quite some time. Most of the stuff doing work with textures and sound and similar to that is already out of the way, all that's left are the 3D models that just baffle me. Either I am dumb/too tired or awful at reading and couldn't understand the tutorials or because they're for the PS2 - I have no clue why I can't grasp the idea behind them, but any help with these few models would be appreciated.

I'd primarily just like to have a way to preview these models, not so much of the converting to some common 3D format for modding and whatnot. Most of the tools I got from the internet specifically for The Sims were for the PC version which obviously are no use in here, and I did try a few tools I found laying around on this forum, but as I said before - it just somehow doesn't go through my head lol


/download removed/
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-29T22:14:30+00:00
- Post Title: The Sims 2 PS2 3D Models

> Reply from Edness ↑Mon Sep 30, 2019 3:24 am at Mon Sep 30, 2019 3:24 am
>
> 
I've been working on a project related to The Sims 2 for the PS2 for quite some time. Most of the stuff doing work with textures and sound and similar to that is already out of the way, all that's left are the 3D models that just baffle me. Either I am dumb/too tired or awful at reading and couldn't understand the tutorials or because they're for the PS2 -what do those tuts tell about getting the face indices?
Autocreation of faces is not recommended here (or it's just a matter of choosing the correct starting points for submeshes):
.



unlock_maid_V1.png (91.81 KiB) Viewed 153 times
## Post #3
- Username: Edness
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 11, 2018 7:26 pm
- Post datetime: 2019-09-30T17:16:48+00:00
- Post Title: The Sims 2 PS2 3D Models

> Reply from shakotay2 ↑Mon Sep 30, 2019 6:14 am at Mon Sep 30, 2019 6:14 am
>
> 
what do those tuts tell about getting the face indices?
Autocreation of faces is not recommended here (or it's just a matter of choosing the correct starting points for submeshes)
I think I've got the face indices set right, though the other two steps kinda just confuse me, though maybe I'm just bad at following steps lol.
Could I at least see what you set for the unlock_maid to get it drawn properly? At least then I could start possibly seeing connections and try to do something with the other files and get it done quicker, I assume
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-30T18:00:30+00:00
- Post Title: The Sims 2 PS2 3D Models

> Reply from Edness ↑Tue Oct 01, 2019 1:16 am at Tue Oct 01, 2019 1:16 am
>
> 
I think I've got the face indices set right,where? how?

> Could I at least see what you set for the unlock_maid to get it drawn properly?well, it's not "drawn properly". It has too many superfluous faces. (Or is the V2 model supposed to look like so?)
The params are "as always" with PS2: shorts, FVFsize 8.
## Post #5
- Username: Edness
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 11, 2018 7:26 pm
- Post datetime: 2019-09-30T18:32:46+00:00
- Post Title: The Sims 2 PS2 3D Models

> Reply from shakotay2 ↑Tue Oct 01, 2019 2:00 am at Tue Oct 01, 2019 2:00 am
>
> 
Edness wrote: ↑Tue Oct 01, 2019 1:16 am
I think I've got the face indices set right, where? how?
Alright, maybe I spoke too soon, I probably don't. Anyway, from what I understood, the face indices would have some form of vague pattern of kinda incrementing values separated with a 00 on either side, though (currently on unlock_lot v1), the closest thing I've found is this, which seems far too repetitive to make any sense to me, eh... I'd assume this is another PS2 thing where most of what's in the tutorial doesn't apply as much? Though I'm not too sure as usual :p

> Reply from shakotay2 ↑Tue Oct 01, 2019 2:00 am at Tue Oct 01, 2019 2:00 am
>
> 
(Or is the V2 model supposed to look like so?)
That I'm not too sure. To my knowledge model_maid is unused (yeah, I probably shouldn't have included that, but oh well.) The models that are definitely used (guessing by their name and seeing in-game effects when swapping files) are unlock_lot v2 and possibly unlock_money v2 & unlock_handyman v2. I can provide some in-game screenshots of some of the used models for reference, if needed.
[HxD_2019-09-30-212734.png](https://xentaxbackup.github.io/file/16834_HxD_2019-09-30-212734.png)
## Post #6
- Username: Edness
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 11, 2018 7:26 pm
- Post datetime: 2019-10-01T14:15:10+00:00
- Post Title: The Sims 2 PS2 3D Models

Still not sure if I'm even on the right track, but I tried putting the whole file (unlock_lot v2 in this case) and seeing if I can find any sensible coordinates that aren't wildly all over the place, the few I did don't seem to be the right ones (or maybe they are?), so eh... Is my general line of thinking at least right? Or is this not the way of 3D models at all?

(same result with hex2obj as well)
[ModelResearcher_2019-10-01-154606.png](https://xentaxbackup.github.io/file/16836_ModelResearcher_2019-10-01-154606.png)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-01T16:09:08+00:00
- Post Title: The Sims 2 PS2 3D Models

> Reply from Edness ↑Tue Oct 01, 2019 10:15 pm at Tue Oct 01, 2019 10:15 pm
>
> Is my general line of thinking at least right?I hope so. Start of vertices is 0x0C9E for me. FVFsize is 8 for hex2obj. (You need to "translate" that into padding/padding intern for the MR.)
## Post #8
- Username: Edness
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 11, 2018 7:26 pm
- Post datetime: 2019-10-02T11:53:36+00:00
- Post Title: The Sims 2 PS2 3D Models

Ah, I think I've finally figured it out :D (A bit broken still, but the general outline is clear, which I think I can probably solve that too) Seems like I was just looking at the wrong places before. Thank you shakotay for making hex2obj
[mesh_viewer_2019-10-02-144627.png](https://xentaxbackup.github.io/file/16843_mesh_viewer_2019-10-02-144627.png)
## Post #9
- Username: al2020
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 13, 2020 7:47 pm
- Post datetime: 2020-11-13T12:18:03+00:00
- Post Title: The Sims 2 PS2 3D Models

Hi, i'm trying to extract two 3d models from sims for ps2. I attacched the two files, i'm trying with meshresearcher but i can't find the correct settings in order to export the mesh.
Can you help me? Thanks
[models.rar](https://xentaxbackup.github.io/file/19019_models.rar)
