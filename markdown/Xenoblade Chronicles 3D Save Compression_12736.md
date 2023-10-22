## Post #1
- Username: moosehunter
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 06, 2011 6:45 am
- Post datetime: 2015-04-01T19:34:16+00:00
- Post Title: Xenoblade Chronicles 3D Save Compression

I've looked at the save files from Xenoblade Chronicles 3D, and unlike the Wii version, the 3DS save files are compressed. The first four bytes of the file are !qzb. It appears that the save format is similar or the same as the Wii version. There is also a dummy empty save file that's used as a placeholder. I wouldn't be surprised if these weren't the same between the 3DS and Wii versions.

Is there any other place this compression is used? Or is there anybody more experienced with compression formats that could take a look at this? I've attached some compressed and uncompressed samples.
[Saves.zip](https://xentaxbackup.github.io/file/8921_Saves.zip)
## Post #2
- Username: MK73DS
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 23, 2015 6:28 am
- Post datetime: 2015-12-22T22:31:25+00:00
- Post Title: Xenoblade Chronicles 3D Save Compression

I'm also trying to decompress Xenoblade Chronicles 3D saves, but I can't find anything 

I tried a lot of methods, zlib, bz2, gzip ... without success 

I found some things, I think that the 0x8B first bytes aren't compressed. I found in this "header" some similarities with the uncompressed Wii version (some "magic" numbers in common, they are just reversed), and we can clearely see the name of the characters so this part doesn't seem to be compressed.
Then, at 0x8C, there are 4 bytes which are the same (only for non empty save ?) : CE FA ED FE
I googled it without succes, I only was able to find that this is the magic number of some old mac binaries or whatever :/

Here is a screenshot with some of the similarities I was able to find : 

Thank's for helping
