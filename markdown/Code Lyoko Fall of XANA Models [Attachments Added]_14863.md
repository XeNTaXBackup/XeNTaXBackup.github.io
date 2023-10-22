## Post #1
- Username: Projectcarthage
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 16, 2016 1:17 am
- Post datetime: 2016-08-15T17:27:27+00:00
- Post Title: Code Lyoko: Fall of XANA Models [Attachments Added]

Hi. So I'm trying to rip from the game "Code Lyoko: Fall of XANA" for Nintendo DS.

So here's the problem. I've been trying for the past several days to get the character/enemy/vehicle models out of this game. This is what I've got at the moment.

I was recommended to use Tinke for ripping things from NDS games. 

Disreguarding the Video files, this is what's in there.

So Then Futurer/ThatTrueStruggle from the VGResource Discord server. wrote a QuickBMS Script to extract the files stored in the data.bf.


None of the files have extensions, so I sorted them by the combination of letters at the end.


This is where the road ends, none of these files make any sense to me. Logically what I'm looking for would be in E3D, but none of the character or enemy names appear. They seem to appear in EBN, EMH, and TXR is probably the textures.

Attempting to load all the files in Tinke, here's the results:
    NANR is "Animation" files, judging by the names, they're sprites.
    NCBR are "Tiles" files, also sprite related. 
    NCER are "Cells" files, sprite related.
    NCGR are more "Tiles" files, has references to both backgrounds and sprites.
    NCLR are palettes.
    NFTR is fonts.
    NSCR is "Maps"
Everything else appears as "Unknown"

So how do I crack these files?
Linked below are what I believe to be model data for one of the enemies, along with what hopefully is the texture.

This is the biggest file of the four, so this likely contains the model.
[http://www.mediafire.com/download/m5cyc ... NKRELA_EBN](http://www.mediafire.com/download/m5cyc18ci2y41fs/BF__NMI_KANKRELA_EBN)

This is the second biggest, not sure what it is.
[http://www.mediafire.com/download/td86d ... NKRELA_EMH](http://www.mediafire.com/download/td86d6n78dcgyuz/BF__NMI_KANKRELA_EMH)

Both of these come from the TXR folder I made, they're the same size, so possibly the same thing.
[http://www.mediafire.com/download/g96fw ... ELATDS_TXR](http://www.mediafire.com/download/g96fw2ra8tdw2lu/BF__KANKRELATDS_TXR)
[http://www.mediafire.com/download/4xbi7 ... NKRELA_TXR](http://www.mediafire.com/download/4xbi7u7sxlefzf8/BF__ENEMY_KANKRELA_TXR)
