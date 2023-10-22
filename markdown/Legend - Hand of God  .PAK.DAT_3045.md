## Post #1
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-05-29T09:52:51+00:00
- Post Title: Legend - Hand of God  .PAK/.DAT

The game "Legend - Hand of God" (demo [here](http://www.gamershell.com/download_22003.shtml)) is a granny3d powered game. In the data forlder the data are archived in pak format, with a dat file linked to every archive. In other words, for every .pak, there's a pak.dat file. I think that the data aren't compressed at all. The pack files simply contain the data archived and the pak.dat files list the content of the pak archive specifying the begin/end for each file. Even if I'm right I don't have a clue about how to read those data...  

In attachment one couple of pak/dat file.

Items.pak (seems to contain uncompressed data. Those are text files evidently):
[](http://img266.imageshack.us/my.php?image=screenhunter02may291147ns8.jpg)
Items.pak.dat (seems the list of the files in the pack with instructions about the begin/end of every file)
[](http://img138.imageshack.us/my.php?image=screenhunter01may291146at3.jpg)
[Data.zip](https://xentaxbackup.github.io/file/1529_Data.zip)
## Post #2
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-05-30T22:38:58+00:00
- Post Title: Legend - Hand of God  .PAK/.DAT

up
## Post #3
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-06-02T06:52:34+00:00
- Post Title: Legend - Hand of God  .PAK/.DAT

ok, that's a noobish question, I know. 
I think I have figured out how every gr2 file start so I suppose I have all the data to iterate through the archive and extract the files.
every .gr2 file starts with this hex:

B867 B0CA F86D B10F 8472

Well   do you know if there's some c++ example that I can look to? Or do you think that this info in enough to create a script for the MultiEx (I don't have a clue of anything, have you noticed?   )?

This would mean that data from this game and from the crazy game trailer park tycoon could be extracted.
## Post #4
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-06-13T19:18:57+00:00
- Post Title: Legend - Hand of God  .PAK/.DAT

really, anyone?
