## Post #1
- Username: ect0s
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 19, 2016 3:24 pm
- Post datetime: 2016-01-19T07:47:46+00:00
- Post Title: Killing Time PC Sprite Format

I'm working to extract and convert all the data in the game Killing Time to a more modern, usable format. 

I've written a few python scripts that extract and decompress(Lzss) chunks of Data from the .rez file (its a BRGR rez, but an old version with differences from Escape Velocity Nova etc). 

I have all the Menus, Textures and Sounds.

The Sprite formats appear to be Run Length Encoded or something similar, but I haven't been able to resolve the encoding scheme. An old tool, XWE can recognize the uncompressed format if its in a .rez file, but it appears to be calculating a few things incorrectly; certain pixels on each sprite are the wrong color or appear corrupted, especially those split from a multiframe image lump. 

About 90% of the split frames render properly in XWE, but the remaining 10% or so have odd glitches. 

Heres a link to some example files:

[http://s000.tinyupload.com/index.php?fi ... 2401149184](http://s000.tinyupload.com/index.php?file_id=12811324312401149184)

This archive contains two sprites, one of the games blue keys, and an enemy. The Blue key was uncompressed in the archive, so I know the data is correct, the Enemy Sprite was compressed, but also appears to have decompressed properly except the last 4 frames; Although Data before and after these sprites extracts perfectly so it might be XWE and not my decompression scheme. I have also included a text file which explains a bit of the format of the Enemy Sprite data lump, as well as its extracted frames.

XWE is far from perfect, it has small pixel errors in even the uncompressed files (although they are mostly usable). I'd like to replace it with my own script if I can figure out how to parse the Sprite image header.
