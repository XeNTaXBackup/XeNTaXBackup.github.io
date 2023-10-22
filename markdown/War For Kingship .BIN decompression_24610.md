## Post #1
- Username: rayleigh
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jul 09, 2015 3:58 am
- Post datetime: 2021-10-17T14:20:38+00:00
- Post Title: War For Kingship .BIN decompression?

Hi
I want to translate the game in my speak but the .BIN Files are Compressed?

Here is the game:
[https://apkpure.com/war-for-kingship-af ... px.skzh.en](https://apkpure.com/war-for-kingship-afk-idle-game/com.fpx.skzh.en)


Sample file:
[https://mega.nz/file/q6ZCwRRC#dq4rf50ZI ... ASNgEvawNs](https://mega.nz/file/q6ZCwRRC#dq4rf50ZIImkW0E6l1LHG5eGautQBxrNfASNgEvawNs)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-28T16:09:17+00:00
- Post Title: War For Kingship .BIN decompression?

Well, this game can't be run anymore. It's crashing on the update screen and it was removed from the google play store.
So if you can't launch the game, you don't need to translate it - problem solved.
## Post #3
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-08-10T16:44:12+00:00
- Post Title: War For Kingship .BIN decompression?

I know this is an old thread for a dead game but it was on the wiki's list of games with unknown formats so I thought I'd take a look anyway.

The game is built with [Egret Engine](https://github.com/egret-labs/egret-core), a HTML5/TypeScript mobile game development engine. As such, all of the game's logic is found in minified JavaScript files making this pretty trivial to investigate.

The BIN files themselves are binary archives that contain a range of different UI assets. They are always in big endian and are usually zlib (raw inflate) compressed post-header. I've extracted, beautified and refactored the core functions for parsing these files which can be found [here](https://gist.github.com/barncastle/addb4287d9e8a6b50e5ba48c0ab931dc) with [UIPackage.loadPackage](https://gist.github.com/barncastle/addb4287d9e8a6b50e5ba48c0ab931dc#file-warforkingship-js-L106) being the primary method. Whilst this isn't functional code, there is enough information for someone to create tooling if ever desired.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-13T11:37:08+00:00
- Post Title: War For Kingship .BIN decompression?

Here's the article for reference:
[http://wiki.xentax.com/index.php/War_For_Kingship_BIN](http://wiki.xentax.com/index.php/War_For_Kingship_BIN)

Thanks for sharing, barncastle
