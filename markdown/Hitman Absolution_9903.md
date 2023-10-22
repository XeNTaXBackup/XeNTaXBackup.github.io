## Post #1
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2012-11-22T09:05:18+00:00
- Post Title: Hitman Absolution

Anyone researching the models from this game? Extension seems to be .pc_resourcelib and I'm curious about bik files tho (.pc_binkvid) but that's another story. If anyone wants some files for models, let me know through PM.
## Post #2
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2012-11-22T15:53:23+00:00
- Post Title: Hitman Absolution

> Reply from CMihai
>
> Anyone researching the models from this game? Extension seems to be .pc_resourcelib and I'm curious about bik files tho (.pc_binkvid) but that's another story. If anyone wants some files for models, let me know through PM.
The files have been given to chrrox for the Xbox 360 version at least.  I'm sure he is figuring it all out.  

As far as the BINK files go, at least on the Xbox 360, all you have to do is delete all the data before the magic header "BIKi" in the files and resave with a .bik extension and they will play just fine.

Video file opened in Hex Workshop -



Part that needs deleted is highlighted -



After deleting the extra part and when you resave as a .bik file -



That's it for BINK video files in the game.
## Post #3
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2012-11-22T16:32:38+00:00
- Post Title: Hitman Absolution

i hate these multiplatform games, they're always so impacked by a bunch of useless scripts, and they don't minimize the game's size in any way.
## Post #4
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2012-11-22T18:12:53+00:00
- Post Title: Hitman Absolution

Thanks for the tip about bik
## Post #5
- Username: Dean
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 09, 2010 6:09 am
- Post datetime: 2012-12-21T22:24:07+00:00
- Post Title: Hitman Absolution

I'm not a big reverse-engineering type guy, but I was looking around the files in Notepad++ and can see that the pc_resourcelib file contains the model, textures and bones, while the pc_headerlib file is obviously some sort of header. The naming system is bizarre. I was able to replace one disguise ingame with another disguise by switching the header/resource file names with eachother. I'm very interested in modding possibilities.
## Post #6
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2012-12-28T04:37:04+00:00
- Post Title: Hitman Absolution

> Reply from Dean
>
> I'm not a big reverse-engineering type guy, but I was looking around the files in Notepad++ and can see that the pc_resourcelib file contains the model, textures and bones, while the pc_headerlib file is obviously some sort of header. The naming system is bizarre. I was able to replace one disguise ingame with another disguise by switching the header/resource file names with eachother. I'm very interested in modding possibilities.

hey, if this is possible, maybe we can visually replace a more useful disguise with one more common to a specific level seeing as how disguises are fucking useless to anyone else wearing it.
