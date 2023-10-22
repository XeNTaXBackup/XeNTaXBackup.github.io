## Post #1
- Username: sparr
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 08, 2022 1:35 am
- Post datetime: 2022-09-07T17:45:36+00:00
- Post Title: VGM Extractor

I'm thinking of rekindling my efforts to make a generic tool that uses other game-specific tools to extract music. Before I go too far on it, I figured this might be a good place to ask if something like it already exists.

This tool won't contain any other tools directly. It is just a sort of meta-tool that would know which other tools to call for each game, how to run those tools, where the games keep their files and metadata, etc.

This is what I have so far: [https://github.com/sparr/vgm-extractor](https://github.com/sparr/vgm-extractor)

For some games it just indexes where the game keeps the music files, e.g. [https://github.com/sparr/vgm-extractor/ ... l%202.yaml](https://github.com/sparr/vgm-extractor/blob/master/gamedata/Portal%202.yaml)

For some games it has some archive metadata with support for calling the relevant tool, e.g. [https://github.com/sparr/vgm-extractor/ ... raria.yaml](https://github.com/sparr/vgm-extractor/blob/master/gamedata/Terraria.yaml) is handled by [https://github.com/sparr/vgm-extractor/ ... #L207-L228](https://github.com/sparr/vgm-extractor/blob/master/vgm-extractor.py#L207-L228)

For some games it has shell scripts (which I might change to python code) that call tools that are part of the game itself, e.g. [https://github.com/sparr/vgm-extractor/ ... s%202.yaml](https://github.com/sparr/vgm-extractor/blob/6709f597c54ca226577e1ab2bf32549a671aa165/gamedata/Team%20Fortress%202.yaml)

For some games I have an idea what is needed, but haven't implemented it yet. see [https://github.com/sparr/vgm-extractor/ ... _TODO.yaml](https://github.com/sparr/vgm-extractor/blob/master/gamedata/TODO/_TODO.yaml)

My goal would be to eventually extend it to support most existing audio extraction tools, such as Unity asset extraction for half the games in the TODO file.

Currently it only handles Steam installed games, but I'd want to make it work for other launchers, and even games installed directly or from OS packages as well.

Does something like this already exist? Is this something folks around here might be interested in if I get it into a more capable state?
## Post #2
- Username: sparr
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 08, 2022 1:35 am
- Post datetime: 2022-09-08T22:28:09+00:00
- Post Title: VGM Extractor

I intended to post this in General game tools. Maybe I misclicked, or maybe a moderator moved it. Either way, would still love to hear from folks who might be interested in this tool.
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-09-09T23:16:25+00:00
- Post Title: VGM Extractor

> Reply from sparr ↑Fri Sep 09, 2022 6:28 am at Fri Sep 09, 2022 6:28 am
>
> 
I intended to post this in General game tools. Maybe I misclicked, or maybe a moderator moved it. Either way, would still love to hear from folks who might be interested in this tool.

Maybe General game tools will be a better category for this topic. I'm moving it back there.

As for the tool - I have never seen something exactly like this (maybe except one low-quality project that was very quickly verified by xentax/zenhax community and banned later), so it may be a good idea to work on this if you really want to make it easier for people to get audio.
## Post #4
- Username: tormatajophil
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 30, 2022 9:35 am
- Post datetime: 2022-10-30T01:43:51+00:00
- Post Title: VGM Extractor

Taking on this type of project would be quite difficult when you think about how many different games use different formats to store data, and even auto-detection would fail a lot of times, since files like PAK aren't standard for all games and have the same extension, but differ in data storage.
## Post #5
- Username: sparr
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 08, 2022 1:35 am
- Post datetime: 2023-01-03T21:20:15+00:00
- Post Title: VGM Extractor

Many games (perhaps 50% of my Steam library) have the bare files just sitting in a directory waiting to be copied and tagged.
Most of the rest follow a few relatively simple patterns (Unity archives, etc).
Truly unique things are rare.

And I'm hopeful that if I ever reach some critical mass of coverage, I'll attract other contributors with access to more games.
## Post #6
- Username: jenx
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 03, 2009 5:26 pm
- Post datetime: 2023-08-12T00:01:04+00:00
- Post Title: VGM Extractor

> Reply from sparr ↑Wed Jan 04, 2023 5:20 am at Wed Jan 04, 2023 5:20 am
>
> 
Many games (perhaps 50% of my Steam library) have the bare files just sitting in a directory waiting to be copied and tagged.
Most of the rest follow a few relatively simple patterns (Unity archives, etc).
Truly unique things are rare.

And I'm hopeful that if I ever reach some critical mass of coverage, I'll attract other contributors with access to more games.

You might want to take a look at these:

[https://github.com/hcs64/vgm_ripping](https://github.com/hcs64/vgm_ripping) - All source code to tools on this page [http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)
Also [https://github.com/hcs64/ww2ogg](https://github.com/hcs64/ww2ogg) (many years since last update)

[https://github.com/vgmstream/vgmstream](https://github.com/vgmstream/vgmstream) - Most up to date of these, includes binaries and libraries

[https://www.scampers.org/steve/sms/other.htm](https://www.scampers.org/steve/sms/other.htm) - "Ravioli Game Tools" This was last updated 2017 but includes a "scanner" engine that probably uses some of the above sources, or maybe all of his own.

[https://github.com/bxaimc/VGMToolbox](https://github.com/bxaimc/VGMToolbox) - Useful for super old 8bit game decryption with a focus on music.

Here's a challenge for you to understand that some popular games/franchises are not just bare files sitting in a folder, or even easily accessible inside archives. Go and extract the music from the Command & Conquer series of games. They change over time, and since about 2007/2008 became somewhat easier, but they previously used a CDATA blob type thing that I don't fully understand that makes it extremely difficult to extract, not impossible, but very difficult. No amount of "byte scanning" or such will give you any type of readable audio format. It was complete gibberish to the community for many years. People, very smart, very dedicated people working on that method for years were eventually able to crack it and get the output to be a continuous stream of a single track instead of thousands of 'chunks' of audio data with no real way to map them together. That was teams of people with years of coding and decryption experience. Then came EA Layer 3 codec, which took another near decade to crack by a community of reverse engineers.

Here's another random example: GTA4 - These days it's fairly easy to extract the music with OpenIV, but if you want to create your own tool, I challenge you to code something that can both read from inside the RPF game archives and reverse engineer the .ivaud format, because it took the combined efforts of a large community years to crack that one too, and I don't think the source code for it is public.

These are just prime random small examples of where you cannot possibly comprehend the complexity of the encryption or ingenuity of the developers and their will power to make their games as secure as possible, especially if the publisher/rights holders make it a bullet point demand on a contract that everything, especially music, must be as encrypted as possible to avoid people doing exactly what you were planning on doing.

I can appreciate and admire your excitement, but making a tool to be as comprehensive as possible that supports literally thousands of games, would take you 10 lifetimes to code yourself, and new games and new encryption methods come out every week, and keeping on top of those too means you would need a near infinite amount of disk drive space to have the assets on hand to reverse engineer them.

I have about 400 games on Steam, with probably about 75% of them (or more) requiring specialized decryption tools, and that's barely 1% of what's available for PC. Users will expect support for Console games as well, so you could add another 40,000+ titles to that list as well. (The figure is probably closer to 400,000 these days but who really knows)...

I don't want to deflate your drive or put you off attempting such a monumental feat, but honestly, you're better off focusing on one or two titles (usually from the same developer) that don't already have tools coded for them yet, and contribute to the overall legacy of tools for the wider community, than to make one all-encompassing tool that you will never stop coding because you won't have enough years in your life or resources to actually cover the vast majority of encrypted games' formats. Fill the gaps in the community rather than trying to reinvent the wheel.
