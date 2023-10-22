## Post #1
- Username: Benjamoose
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 01, 2016 2:10 am
- Post datetime: 2022-01-13T02:44:54+00:00
- Post Title: [PC] Ghostbusters: The Video Game Remastered - TEX Files?

Hi there! Long time lurker/downloader, first time poster.
I've done a lot of Google searching and a bunch of forum searches, so forgive me if I've missed an update regarding this.

I'm working on several mod projects, but I'm hitting a roadblock regarding Ghostbusters TVGR's TEX format.
From what I understand (from searching this forum), TEX files are just regular files (DDS/TGA) that have some shenanigans done to the headers?

Anyways, my problem isn't so much getting the textures out (I've found a million and one tools that'll do that job just fine, including some made on this forum specifically for the game), but I've yet to find anything that can do it reliably and also then convert them back?


Summary: I'm trying to convert the game's TEX files to a usable format and back again for repacking/modding.

I've tried the [TEX2DDS tool](https://forum.xentax.com/viewtopic.php?t=4392) for the game made on this forum, but all it does is output an unusable DDS (and seemingly has no way to convert back to TEX). Same for some [Noesis plugins](https://forum.xentax.com/viewtopic.php?t=15685#p125821); they can read the file but can't turn it back into a packable TEX.

I've found a few converters that work by dropping TEX files onto an .exe which then converts files back to TEX in the same manner, but literally anything I've found/tried has just ended up with the modified texture not loading in-game (pink and green checkerboard).

Here are some example files (they were obtained via [this extracting tool](https://zenhax.com/viewtopic.php?t=12615#p51384)):

- [Ray Stantz Head Textures (TEX)](http://benjaminrudman.com/temp/stantz.zip)
## Post #2
- Username: Benjamoose
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-01-13T22:29:10+00:00
- Post Title: [PC] Ghostbusters: The Video Game Remastered - TEX Files?

You may have some issues with importing because this file format contains one 16-byte HASH field and one 4-byte CRC field (probably).
So if those values are not calculated correctly during import then check function in game fails and you are not able to mod the game.
You can test this theory by changing one random byte in image data in original TEX file - if texture isn't displayed properly after this change, it means that game is protected and CRC/HASH functions need to be reverse engineered to proceed.

By the way, here is file format of TEX file [http://wiki.xentax.com/index.php/Ghostb ... stered_TEX](http://wiki.xentax.com/index.php/Ghostbusters:_The_Video_Game_Remastered_TEX)
## Post #3
- Username: Benjamoose
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 01, 2016 2:10 am
- Post datetime: 2022-01-13T23:35:13+00:00
- Post Title: [PC] Ghostbusters: The Video Game Remastered - TEX Files?

> Reply from ikskoks ↑Fri Jan 14, 2022 6:29 am at Fri Jan 14, 2022 6:29 am
>
> 
You can test this theory by changing one random byte in image data in original TEX file - if texture isn't displayed properly after this change, it means that game is protected and CRC/HASH functions need to be reverse engineered to proceed.

Hey! Thanks for the reply.


I'll give that a shot and report back. At the very least it'll be useful public information, I imagine.


> Reply from ikskoks ↑Fri Jan 14, 2022 6:29 am at Fri Jan 14, 2022 6:29 am
>
> 
By the way, here is file format of TEX file http://wiki.xentax.com/index.php/Ghostb ... stered_TEX

Thanks for the link/info. I have a friend who is also looking into this with me and I'm sure they'll find this useful!
