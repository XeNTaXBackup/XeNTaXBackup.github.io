## Post #1
- Username: sskillz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 18, 2012 5:14 pm
- Post datetime: 2012-08-18T09:21:02+00:00
- Post Title: Trying to modify a Unreal Engine 3 Compressed Package

Hello,
I've decompressed a Unreal Engine 3 package using this tool from gildor.org (Unreal Package Decompressor).
And I found the address of the variable I wanted to to modify and changed it using a hex editor (Was just a single byte).
But now I need to compress the package back so the game won't notice it changed because right now as uncompressed 
the game crushes with KERNELBASE.dll fault.

The game is Tribes Ascend, free game on steam, and I just the speed of one of the projectiles and I want see its effect on the training map (Projectiles
are server side, so this won't be used for hacking )

Do you know which compression did they use?
Do you know how I go about recompressing it? 
Does packages normally have a checksum that I might have broken? 
Any other ideas?


I've attached one of the smallest compressed packages that come with the game, it can be decompressed using the tool I mentioned.
Thanks ahead.
[Core.zip](https://xentaxbackup.github.io/file/5683_Core.zip)
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-08-19T08:43:31+00:00
- Post Title: Trying to modify a Unreal Engine 3 Compressed Package

Hmm, strange. I know that UE3 games can read uncompressed packages fine, I've modified packages this way for ME3 but with my own tool for decompressing, perhaps gildor's tool doesn't fix the header properly?

It would be more appropriate to ask about that on gildor's forum.
