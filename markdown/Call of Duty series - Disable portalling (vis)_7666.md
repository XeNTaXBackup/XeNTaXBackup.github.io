## Post #1
- Username: CoDEmanX
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 12, 2009 1:39 pm
- Post datetime: 2011-11-10T23:02:57+00:00
- Post Title: Call of Duty series - Disable portalling (vis)?

Hello Xentax-members,

i look for a way to disable the ingame portalling of Call of Duty 4 and above.
I wonder if it's possible, it would be really useful for the modding community - the stock maps could be remade for other titles of the franchise.

there is no dvar to turn off portalling. But there is an interesting one: r_singlecell
If enabled, only the portal the player is in will be drawn.

What i want is the opposite, show all cells at the same time in order to snapshot the map (3d ripper dx).
Does anybody know how to achieve this? Maybe Assambly-experts or memory hackers?

Might there be a single byte, specifying the number of cells drawn, which could be replaced by 9999?
Or DLL-injection to intercept the portal functions... ?

Thanks in advance!
## Post #2
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-11-19T08:47:34+00:00
- Post Title: Call of Duty series - Disable portalling (vis)?

Is 'portalling' something like 'only displaying seen, predefined chunks'? Never heard that word before...

Maybe the game is using LOD (Level Of Deail) for each chunk, I guess each chunk has its own LOD level
I would set if LOD = 0 to hide it/unload it.
Maybe you can try fiddling with LOD commands (if there are any)
