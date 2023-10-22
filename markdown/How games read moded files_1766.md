## Post #1
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-03-06T12:33:44+00:00
- Post Title: How games read moded files?

One more thing before I drag myself back into my shell.   
I know 2 games which have all files in containers *.cat format. But since they were meant to mod the *.cat files can easily be open and any file inside modded. 
But now is the funny part. 
Modded files HAVE to be placed next to *.cat file and thats where they are read by the game. So actually the files in *.cat are always safe backup of the originals. 
My question is: is this something which works always (standard) in most games this way? Or the game exe needs to be programed to read its files in this very manner?
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-03-06T13:16:16+00:00
- Post Title: How games read moded files?

That is entirely up to the programmers of the game. A lot of games use an identical trick, though. 

In a way, they use a .cat file (in this case) as a file stream, along with directory structures and all. They have an interpreter/intermediate/CAT-OS whatever you call it, that can be used as any file path and will do all the addressing/decompressing etc as needed by the archive structure. The game will just call a load routine and the CAT-OS will load the file from the CAT. 

In case of your game, the authors have probably programmed a routine to check whether the file of interest to the game is present in the folder of the .cat file (more often than not also keeping the same directory structure). If not found, it will use the .cat as the file stream. 

In many cases the game will just use the .cat (or any other archive type) as stream, or even just to load stuff from. Naturally, it can be a pain for authors to have to build a new archive each and everytime they just change a few scripts, sounds, textures etc and they wish to view the result in the running game. That's why some opt to build in this other stream method, where files are actually read from the OS file paths and not the .cat file paths. I reckon a lot of games these days do this though: start off with reading individual files from the hard drive and when all is done and the game should go gold, pack everything in a few archives to ship with the game. That's why you often see the filenames saved in the archives, complete with folders from the root directory. 

In short: it's up to the authors to build this in and having it turned on in the retail version.
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-03-08T21:06:12+00:00
- Post Title: How games read moded files?

I have found this to be the case in many games, but the game developers don't really care to mention it.

I think the main reason why this exists is to aid the developers rather than the modding community. For example, when the game is being developed, it isn't uncommon that the graphic artists will be changing and tweaking images - so rather than having to rebuild the main archive for every change, they can simply place the file in the directory and tell the game to reload that 1 image - quick, simple, and thankfully for modders the code is often left in the final version of the game.

However, the more files there are outside the main archives, the less efficient the game will be, mainly because the hard drive must constantly change between different files, which are potentially in totally different areas of the disk, and file buffering is not as successful as there would be some overhead when changing between files.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-03-08T22:47:24+00:00
- Post Title: How games read moded files?

It is perhaps not exactly related to container files, but also important in case of reading bitmaps with transparency (layers) by the programs. Or even various data files for that matter. The programs will read them in alphanumerical order. So for example if one wants the road be displayed over the land the layer with road better be named 1road.xxx or  and land 2land.xxx, or else we wont see the road ever.
## Post #5
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2006-11-11T00:53:10+00:00
- Post Title: How games read moded files?

> Reply from friendsofwatto
>
> 
However, the more files there are outside the main archives, the less efficient the game will be, mainly because the hard drive must constantly change between different files, which are potentially in totally different areas of the disk, and file buffering is not as successful as there would be some overhead when changing between files.

Not quite the case. The game will typically decompress all the vertex and bitmap data it can and will store this in the GPU memory. Not only does this increase speed (you can also optimize the position of the vertices within memory to get even more speed by reducing the amount of time you have to spend looking for stuff within VRAM) but it frees up traditional RAM, where sounds, the actual program code, stuff that doesn't fit into VRAM, etc. will be stored. The only time a program needs to access the hard disk is when an instance of an entity for which it doesn't have resources for appears. Actual level geometry/trees are also needed upon level changes, obviously.

The net result is that load times may be a bit longer, although a clever programmer could theoretically circumvent this through an Oblivion-like system where external data files can actually be pre-selected and will automatically load upon game start. If you want to remove a particular file, just remove the check next to it.

Granted, fragmenation will definitely add some length to those dreaded load screens, but if you defragment your disk regularly and/or use a RAID configuration, it shouldn't be an issue. Hope I've answered some questions
