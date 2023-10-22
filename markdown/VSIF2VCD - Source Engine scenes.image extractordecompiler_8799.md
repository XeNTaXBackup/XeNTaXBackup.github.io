## Post #1
- Username: SiPlus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 05, 2011 6:30 pm
- Post datetime: 2012-04-20T11:45:50+00:00
- Post Title: VSIF2VCD - Source Engine scenes.image extractor/decompiler

I see nobody ever tried to extract scenes from scenes.image. So I decided to write a command line decompiler for it.

Usage: VSIF2VCD "game directory"
Game directory is where gameinfo.txt is located. It must include:

scenes/scenes.image
maplist.txt - a text file listing all maps in the game, with Windows line separator.
maps/<map name>.bsp or maps/<map name>_l_0.lmp - for each map in maplist.txt.

Download and sources: [https://skydrive.live.com/redir.aspx?ci ... 5CD82A!188](https://skydrive.live.com/redir.aspx?cid=65b4d1e61b5cd82a&resid=65B4D1E61B5CD82A!918&parid=65B4D1E61B5CD82A!188)
More info: [https://developer.valvesoftware.com/wiki/VSIF2VCD](https://developer.valvesoftware.com/wiki/VSIF2VCD)
