## Post #1
- Username: akumalol
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 14, 2010 7:14 pm
- Post datetime: 2013-03-23T10:19:47+00:00
- Post Title: Heroes of Order & Chaos hacking

Hello all,

I tried doing some progress on hacking HOC iOS game so i will post my results and maybe someone smarter can pickup from there and hack this game.

If you do please share your hack to the community! 

I made three attempts of hacking. 

1) Using iFile i renamed the file located on HOC folder from "model_phy.bin" to "model_phy.bin.old".
I thought this will enable me a wallhack but the only thing is did is made my hero go through the barracks. 
Also if you do that in a game and go through the barracks after some time the game kicks you back on the main menu.

2) I tried iGameGuardian to change the value of the skill points. It was simple enough. The skill points are the points that are available once you level up. For example, at first you have 1 skill point and you use it to select your hero skill. When you level up you get one more to select another hero skill etc. 
I changed the value of my hero skills succesfully but after playing for a while it kicked me back to the main menu.

I think in both ways the server is checking if something weird is happening to the game and kick out players. (the server might think i am out of sync)

3) I tried decompiling *.bin files from the game. All the bin files are ZIP files with a modified header. If you want to open the bin files just open them with a hex editor and do the following:

Search for: 47 42 4D 50
Replace with: 50 4B 03 04

and save.

After that you will be able to see and extract all the files from the archive. But if you try to change a file and repack (by changing the headers again to original) the game will crash.

So i am stuck on how to repack the game files without the game crashing the game.

Let me know if you guys know anything that might help. 

Cheers!
