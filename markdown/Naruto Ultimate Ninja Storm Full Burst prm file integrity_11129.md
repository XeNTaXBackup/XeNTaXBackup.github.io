## Post #1
- Username: Cybore
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 28, 2013 1:51 pm
- Post datetime: 2014-01-12T06:09:41+00:00
- Post Title: Naruto Ultimate Ninja Storm Full Burst: prm file integrity

Hey guys, 

It's my first post here. I was curious if somebody in here could help me figure out this problem I am having with the file integrity check, located in the header of the prm files below.  I do moveset modding for this game and I am currently able to modify the files to the extent that the filesize does not change.  This however is really limiting as there are sections where there isn't sufficient room to put something in, which is why I am looking for a way for the game to accept my file size changes.  I know this is possible as there is a chinese modder who has put files that have changed filesizes (attached below) that load fine.  I am almost completely certain that these few bytes are what are causing the game to crash, but I've tried everything and can't seem to be able to change the filesizes of my files. 

[](http://www.mediafire.com/view/5k84c84ssj4ttyr/Mod.png)

I've even tried copying these few bytes from another file that serves the same purpose and matching file sizes, but the game still crashes.  I saw no correlation between bytes added and how these few values changed.  I am thinking perhaps these few bytes check the location of certain values, but I really have no clue.  I thought it was worth a shot posting here in case somebody had seen something similar before. These files where decypted with the generations cpk_unpacker that was posted here a while back.

Here are a few sample files.  Two original files and two modded files with changed file sizes that load properly.  The integrity check is located at offset: 330. 

[http://www.mediafire.com/download/xfaoq ... Orig.xfbin](http://www.mediafire.com/download/xfaoqa61cwbay3y/Orig.xfbin)
[http://www.mediafire.com/download/x63gv ... rig2.xfbin](http://www.mediafire.com/download/x63gvj3zd1qzmup/Orig2.xfbin)
[http://www.mediafire.com/download/1h05f ... /Mod.xfbin](http://www.mediafire.com/download/1h05fsttc5wlfdd/Mod.xfbin)
[http://www.mediafire.com/download/qbjty ... Mod2.xfbin](http://www.mediafire.com/download/qbjtyy7dnnnaa5j/Mod2.xfbin)

Thanks again
