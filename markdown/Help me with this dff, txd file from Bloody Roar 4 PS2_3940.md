## Post #1
- Username: chazzy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 14, 2009 7:13 pm
- Post datetime: 2009-12-14T11:51:29+00:00
- Post Title: Help me with this dff, txd file from Bloody Roar 4 PS2

Hi.
I'm trying to convert dff, txd file from Bloody Roar 4(dff sample attached).
I googled and found out that this is renderware file and also found out that GTA uses this format too.

So I tried several tools made for GTA but all failed.
I guess BR4 uses different encryption.

can anybody help me please?
(sorry for poor english. I'm not native speaker)
[0000_01_ps2.zip](https://xentaxbackup.github.io/file/2610_0000_01_ps2.zip)
## Post #2
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-01-10T21:23:57+00:00
- Post Title: Help me with this dff, txd file from Bloody Roar 4 PS2

I guess BR4 uses different encryption.

can anybody help me please?
(sorry for poor english. I'm not native speaker)[/quote]
I am interested in Bloody Roar 4, but what you posted makes me even more confused.
I'll start with the name .dff
I think this extension might be used in several unrelated RenderWare games.
I say this because I have seen "Deer Avenger 4" a PC game use .dff and I have also "Scooby Doo: Night of 100 Frights" a Ps2 game use the same format, but both of these are different than the GTA .dff format

As for Bloody Roar 4 itself, it is interesting that your sample file is compressed. I'm assuming it's not encrypted because I can still make out with my eyes the corrupted text "Softimage" and "BONETAGE=21". Both text strings are also found corrupted many times in memory dumps done on a PS2 Emulator.
Now there are still two mysteries about this game:
Is it really compressed because the older game Bloody Roar 3, is found on a CD, not a DVD, because it is a small game, like Tekken Tag Tournament. Since BR4 adds new characters they might have compressed it to make it fit on a CD, for lower production costs.
The other possibility is that like, BR1,2,3 the meshes are generated when the game is run, like Spore.
From the memory dump a friend gave me, it appears that the meshes are Not made "on the go" and really just regular generic type ps2meshes (BR4 had 2 co-developers, so it's graphics are very different.
I'll upload a sample of the memory dump (the main RAM, not VRAM which is GPU dependent). I got pieces of arms, tails and heads, to import into blender from BR4 and BR3. It was during finals week so I didn't refine my method to get the whole mesh. I'll post more tomorrow.
The link [http://ps23dformat.wikispaces.com/file/ ... EMDUMP.bin](http://ps23dformat.wikispaces.com/file/view/BR4MEMDUMP.bin)
## Post #3
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-01-11T00:10:41+00:00
- Post Title: Help me with this dff, txd file from Bloody Roar 4 PS2

Sorry for the double post, but I did some exploring: Here is a picture of a mesh from Bloody Roar 4. This only makes me more confused. Is it a Collision mesh? Then why does its abs look ripped? And what about the Octagons on the lower chest? Bloody Roar 2 for the PS1 also seems to have a Hexagon where these octagons are.
## Post #4
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-01-12T21:29:09+00:00
- Post Title: Help me with this dff, txd file from Bloody Roar 4 PS2

doesn't look like much of a collision mesh. maybe its for shadow
## Post #5
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-01-19T22:21:42+00:00
- Post Title: Help me with this dff, txd file from Bloody Roar 4 PS2

The format is a modification of the "standard" PS2 tri-stripes. The problem is that there are different mesh systems that seem to be inter-wound with the character meshes (at least in memory dumps)
Mesh vertex are stored in sections that begin with:
00 00 00 05, 04 01 00 01, 00 80 XX 68
followed by the vertexes
and end with:
Padding
00 00 00 05, 04 01 00 01, 01 80 XX 64

However their is a different type of geometry found along side that has:
05 01 00 01
Here is a picture of a head. The hair and eyes are not in the picture.
## Post #6
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-01-22T02:09:39+00:00
- Post Title: Help me with this dff, txd file from Bloody Roar 4 PS2

> Reply from chazzy
>
> Hi.
I'm trying to convert dff, txd file from Bloody Roar 4(dff sample attached).
I googled and found out that this is renderware file and also found out that GTA uses this format too.

So I tried several tools made for GTA but all failed.
I guess BR4 uses different encryption.

can anybody help me please?
(sorry for poor english. I'm not native speaker)
Hey Chazzy I'm posting Gado in Beast form (He's a Lion).
I had to use a hexeditor, once I learn some programming I can make a proper script.

[http://ps23dformat.wikispaces.com/file/ ... Gado.blend](http://ps23dformat.wikispaces.com/file/view/LionGado.blend)
