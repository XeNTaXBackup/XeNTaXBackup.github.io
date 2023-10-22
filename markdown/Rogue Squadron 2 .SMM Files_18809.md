## Post #1
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2018-09-14T18:48:54+00:00
- Post Title: Rogue Squadron 2 .SMM Files

I suspect .SMM files found in Rogue Squadron 2's data are models.
Nothing much more i can say at the moment.

Here's a sample file for a TIE Fighter so maybe someone else can take a look(and maybe make a script to import it into 3DS Max or Noesis if it is indeed a model?)
[https://cdn.discordapp.com/attachments/ ... e_crft.smm](https://cdn.discordapp.com/attachments/419711036837330956/490231602115510280/tie_crft.smm)
Im not skilled enough in these kinda things to do it myself
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-09-15T00:14:41+00:00
- Post Title: Rogue Squadron 2 .SMM Files

your smm sample looks like texture data to me and being a Gamecube game could be one of nintendo texture formats.
[https://github.com/Zheneq/Noesis-Plugin ... ndo_tex.py](https://github.com/Zheneq/Noesis-Plugins/blob/master/lib_zq_nintendo_tex.py)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-15T08:16:03+00:00
- Post Title: Rogue Squadron 2 .SMM Files

funny, an animated parser! 



smm-nintex.jpg (92.28 KiB) Viewed 51 times

Format seems to be NINTEX_CMPR   = 0x0E
,  a little bit swizzled
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-09-17T01:36:54+00:00
- Post Title: Rogue Squadron 2 .SMM Files

need more samples to complete the script  



tie_crftout.png (177.9 KiB) Viewed 39 times



actual size is 1024 x 1024, had to scale it down to fit in attachment.   
image data starts at 0x40, there is a footer too, not sure what it is.
i don't really see where is width and height info stored yet unless
is obfuscated in header or maybe stored in another file.
