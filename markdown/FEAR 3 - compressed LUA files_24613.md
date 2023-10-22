## Post #1
- Username: FromDarkHell
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 18, 2021 5:37 am
- Post datetime: 2021-10-17T22:58:18+00:00
- Post Title: FEAR 3 - compressed LUA files

Feeling a bit stumped on this one so I'm going to ask for help here. 
FEAR 3 has it's archive format in the form of *.dspack files. I'm trying to figure out the (proprietary?) algorithm for the compressed files in the archive.
There's a QuickBMS script for dumping out the files in the dspack's which works for some of them and there's the [Game Extractor](https://github.com/wattostudios/GameExtractor/blob/master/src/org/watto/ge/plugin/archive/Plugin_DSPACK.java#L151) which seems to do a better job on all of the files (due to endian-ness it seems). I don't know enough about QuickBMS to fix that right now, but that's not what I'm looking for right now.


I noticed that the game uses Lua for it's scripting and I'd like to tear into that and see what random stuff I can find in it.
But the most of the Lua files are compressed so I can't just put the decompiler at them and get code out from it.
Sample Files: [Link](https://drive.google.com/drive/folders/11qs8mkUw6dIukGpAwxHnMpe4kI5_blg8?usp=sharing)

If nothing else, feel free to shoot me some pointers on how to get started reversing this, I'm comparatively new to reversing stuff like this so I don't really know where to start!
