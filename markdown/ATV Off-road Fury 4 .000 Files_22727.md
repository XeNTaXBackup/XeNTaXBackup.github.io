## Post #1
- Username: Omarios
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 21, 2020 3:28 pm
- Post datetime: 2020-09-21T07:30:40+00:00
- Post Title: ATV Off-road Fury 4 .000 Files

So I’ve been trying to modify ATV Off-road Fury 4 for quite some time now. I’m no expert in programming and what not but I’ve tried my best to get information from here and there about modding PS2 games.

What I’m aiming for is really simple actually, just modifying AI names, and swapping their in-game gear color. But the problem is that, as I said, I’m not in an expert in this matter. The game has a ton of .000 files which I do really believe hold the game’s resources and assets, but the problem is that I can’t seem to open it. A google search of the file format gives back several results so I thought I’ll ask here to see if people know anything. I should also add that all the .000 files are 2048KB in size.

How do I open and view the contents of .000 files?

I should also mention that while viewing some files through a hex editor, I found some interesting stuff. Files such as resources/root/setup/aiplayercolours.xml. The main problem is that I don’t know how to get to these files. 
I’m honesty tired of running around clueless trying to do this, I’m willing to pay if someone has the knowledge of doing this.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-09-21T09:26:19+00:00
- Post Title: ATV Off-road Fury 4 .000 Files

> What I’m aiming for is really simple actually, just modifying AI names, and swapping their in-game gear color.
If it is the only thing you are trying to achieve then Cheat engine and Texmod + pcsx2 should do the trick.

> while viewing some files through a hex editor, I found some interesting stuff. Files such as resources/root/setup/aiplayercolours.xml. The main problem is that I don’t know how to get to these files.

If you have filenames, then maybe offsets and sized are stored in the same files.
Read some tuts here [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
and try to unpack files with quickbms.
## Post #3
- Username: Omarios
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 21, 2020 3:28 pm
- Post datetime: 2020-09-21T22:12:41+00:00
- Post Title: ATV Off-road Fury 4 .000 Files

> Reply from ikskoks ↑Mon Sep 21, 2020 5:26 pm at Mon Sep 21, 2020 5:26 pm
>
> 
What I’m aiming for is really simple actually, just modifying AI names, and swapping their in-game gear color. 
If it is the only thing you are trying to achieve then Cheat engine and Texmod + pcsx2 should do the trick.
while viewing some files through a hex editor, I found some interesting stuff. Files such as resources/root/setup/aiplayercolours.xml. The main problem is that I don’t know how to get to these files. 

If you have filenames, then maybe offsets and sized are stored in the same files.
Read some tuts here viewtopic.php?f=29&t=22266
and try to unpack files with quickbms.

I'm not sure if quickbms has a script to extract the folders from this game? As I said, I found some files but they're in SCUS files of the game, Archive.imp does contain some files, and Archive.bin is total gibberish which I can't understand.
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-09-22T06:37:03+00:00
- Post Title: ATV Off-road Fury 4 .000 Files

I don't really know this game or it's files, so I can only guess based on what you told in this topic,
but SCUS/SCES files are main executables and they often contain some filenames, sizes and offsets. You can call it LBA tables or data arrays.
If not in exe, then this data is stored in archive itself or in some index file. It is job for you to figure it out.

If you don't have reverse engineering knowledge, then just use cheat engine and texmod or edit data directly in hex editor - it is an easy solution for you.
## Post #5
- Username: Omarios
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 21, 2020 3:28 pm
- Post datetime: 2020-09-25T08:16:30+00:00
- Post Title: ATV Off-road Fury 4 .000 Files

The first 4 bytes of the archive are 69 4D 70 30.

Unfortunately I don't think that there is a current script for this type of file.
