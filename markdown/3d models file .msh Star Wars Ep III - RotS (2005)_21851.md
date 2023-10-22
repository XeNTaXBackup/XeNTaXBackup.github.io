## Post #1
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-03-07T15:12:13+00:00
- Post Title: 3d models file .msh Star Wars: Ep III - RotS (2005)

Hello, again with this game,I need someone with knowledge to create a .bms script or for Noesis to extract the 3d models from the .msh files of the game "Star Wars Episode III - Revenge of the Sith" 2005 (xbox). I already have the method to extract them one by one (submeshes), but it is extremely long and boring, i use hex2obj. I thank in advance the person who could help me.

I put some samples of .msh files:
[https://www.mediafire.com/file/etu35wlg ... s.rar/file](https://www.mediafire.com/file/etu35wlgn5vf5r5/Samples.rar/file)

Here is the only discussion that talks about the game: [viewtopic.php?f=16&t=12359](https://forum.xentax.com/viewtopic.php?f=16&t=12359)

Thank you
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-07T15:45:52+00:00
- Post Title: 3d models file .msh Star Wars: Ep III - RotS (2005)

> Reply from SilesVyr ↑Sat Mar 07, 2020 11:12 pm at Sat Mar 07, 2020 11:12 pm
>
> I already have the method to extract them one by one (submeshes), but it is extremely long and boring, i use hex2obj. 
[...]
Here is the only discussion that talks about the game: viewtopic.php?f=16&t=12359

Thank youhex2obj was NEVER intended to be used for extracting many submeshes- just the first 2 or 3 ones "to get the idea"
- there are follower tools (Make_H2O, Make_obj) which take care of several submeshes.

Why not use the tool mentioned in the thread you linked above ?
.



darthvader.msh.png (90.66 KiB) Viewed 103 times
## Post #3
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-03-07T16:25:32+00:00
- Post Title: 3d models file .msh Star Wars: Ep III - RotS (2005)

Make_H2O_StarWarsEp3-XBOX.zip doesn't really work nice, sometimes it misses polygons, sometimes it doesn' t find any 3d model, not for vader (lol) but for lsaberanakin.msh it doesn't see model. I know hex2obj isn't intended to be used for extracting many submeshes, but often I had to do it by hand because something was missing. I just need a script to open them, working for every msh files.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-07T16:41:12+00:00
- Post Title: 3d models file .msh Star Wars: Ep III - RotS (2005)

> Reply from SilesVyr ↑Sun Mar 08, 2020 12:25 am at Sun Mar 08, 2020 12:25 am
>
> 
Make_H2O_StarWarsEp3-XBOX.zip doesn't really work nice,Works nice for most models - you're the first one who's complaining! 

> sometimes it misses polygonsFor which models, please?

> sometimes it doesn' t find any 3d model, not for vader (lol) but for lsaberanakin.msh it doesn't see model.lsaberanakin.msh is a very small model file, 1 submesh, iirc. You can easily extract it by hand. But FVFsize is 36 here, not 44!
.



lsaberanakin.msh.png (23.93 KiB) Viewed 84 times



> I just need a script to open them, working for every msh files.Yeah, then you need to wait 'till somebody feels obliged to fulfill your needs.
