## Post #1
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2013-08-30T14:58:48+00:00
- Post Title: God of War 1 (PS2, or PS3 GoW Collection)

A long time ago I came by and asked for some help extracting models from this game.  The guys who responded were very knowledgeable and helpful, and while we weren't able to figure it all out at the time I was able to work with another guy who did.  For those interested -> [http://ps23dformat.wikispaces.com/God+of+War](http://ps23dformat.wikispaces.com/God+of+War)

Anyway, now I'm back at it trying to figure out more of the WAD files.  Ideally I'd like to understand it enough to write a quick utility that would take a WAD file and break it up into its component parts (Either by actually creating separate files, or just having a nested-list style interface for modifying).

Using the entrance to Pandora's Temple as an example:
WAD_Pand00B
  GFXX_Pand00B
    GFX_fog
    GFX_metalBloody01
  TXRX_Pand00B
    TXR_defFogText
    TXR_file79
  MDLX_Pand00B
    MDL_DoorCrank
    MDL_Sparkle2

And so forth.  I don't particularly care about the above sections, they were just the first few I came across in the file.  Though having a model extractor/injector would be pretty nifty if it handled the textures and everything else that went along with it.

The WAD file appears to open with an index.  The sections aren't in order of their index pointer, but GFXX is 0c, TXRX is 07, MATX is 08 and so forth.  I haven't checked thoroughly but it appears that the numbers would combine to form a complete sequence from 1 to 23(hex).

Chunks of the file are enclosed in the text GroupStart and GroupEnd, with groups being nested.  I believe one groupstart/groupend file would contain the entirety of MDLX_Pand00B, which itself would contain many start/end blocks for each individual model.  At a quick glance, the MAT_ sections would appear to have a GroupStart, but instead of GroupEnd they have ff ff ff ff followed by the name of the MAT.

The latest thing to catch my interest are the ESC_ sections of the WAD.  These appear to initialize the level data and contain level triggers.  I've been able to skip cutscenes and prevent enemy spawns by zeroing out the calls in these sections, but I'm doing it rather clumsily.  Help understanding their makeup would be appreciated.

Anyway, before I ramble on too much and fill this topic with a paraphrased hexdump, is there anybody else interested in this game that wants to work together on it?
## Post #2
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2013-09-09T14:05:14+00:00
- Post Title: God of War 1 (PS2, or PS3 GoW Collection)

Alright, not sensing a lot of interest in the WAD files.  How about the save files?  Is anybody good at figuring out checksums?

I've installed debug firmware on my PS3 and have figured out a number of interesting ways to modify the save file, but haven't figured out the checksum it applies.  Long story short, I can modify all these things in memory for myself but can't write a savegame editor to allow others to modify their saves until I figure out this checksum.
## Post #3
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2013-09-11T14:35:45+00:00
- Post Title: God of War 1 (PS2, or PS3 GoW Collection)

If anybody was interested in the save file checksum, I figured it out here:
[viewtopic.php?f=30&t=10767](http://forum.xentax.com/viewtopic.php?f=30&t=10767)

Think I'm gonna take a break from trying to figure out the WADs for a while.
