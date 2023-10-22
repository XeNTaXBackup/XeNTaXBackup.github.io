## Post #1
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2014-10-11T21:43:16+00:00
- Post Title: SpongeBob SuperSponge (PSX) BIGLUMP.BIN

I want to extract the music from this game, they songs are in FastTracker II .xm format. I can use standard file ripping tools to extract the files fine, but they always come out looking corrupt and odd.
I'm not sure how the data is stored in this game's archive, but here's a picture of how the .xm files look when loaded in OpenMPT:

I'm not sure if it's xored or compressed in an odd way or what. I can extract the samples separately using PSound, but they're unnamed. I'd hope the sample data would be IN the .xm.

Here's the first 1MB of the file, it actually has a module in it around 85000 bytes -
[http://puu.sh/c7sYm.001](http://puu.sh/c7sYm.001)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2019-01-05T23:12:40+00:00
- Post Title: SpongeBob SuperSponge (PSX) BIGLUMP.BIN

You should be able to proceed by looking through game source code [https://github.com/philosophofee/SBSPSS](https://github.com/philosophofee/SBSPSS)
You can start with files makefile.gaz, makefile.gfx and of course "\data\Music\" folder.
