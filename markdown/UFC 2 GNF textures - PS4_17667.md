## Post #1
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2018-02-06T06:27:03+00:00
- Post Title: UFC 2 GNF textures - PS4

Hi guys. 

Need help with the textures for the UFc 2 game on the ps4. The textures are in a format called GNF. The data in the texture looks like a dds file in a hex editor, but the header is different. 

Here's a sample of the file:

GNF texture: [http://www19.zippyshare.com/v/Eb6icRWi/file.html](http://www19.zippyshare.com/v/Eb6icRWi/file.html)
## Post #2
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-02-06T17:50:06+00:00
- Post Title: UFC 2 GNF textures - PS4

i'd need more files. potentially some that have transparency. necessary to get the format byte. texture finder shows the blocks are shuffled anyway. that'd need some time to sort. or maybe you get somebody better with shuffles. gotta wait for acewell i figured he knows those noesis shuffle algos, better then me.
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-06T18:51:11+00:00
- Post Title: UFC 2 GNF textures - PS4

Noesis has native support for PS4 gnf textures   
but on the technical side this is all i know 

> For example, about .GNF textures: the pixels don't follow the traditional order (row, row, row...column, column, column), but they're organized and arranged on a Peano's curve. This allows a better use of the system's cache.
[http://www.assettocorsa.net/forum/index ... ipt.44497/](http://www.assettocorsa.net/forum/index.php?threads/console-development-conference-video-transcript.44497/)
## Post #4
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2018-02-07T11:00:08+00:00
- Post Title: UFC 2 GNF textures - PS4

> Reply from episoder
>
> i'd need more files. potentially some that have transparency. necessary to get the format byte. texture finder shows the blocks are shuffled anyway. that'd need some time to sort. or maybe you get somebody better with shuffles. gotta wait for acewell i figured he knows those noesis shuffle algos, better then me.

The diffuse and spec maps are supported in Neosis, but the normal maps don't display correct. Here's a sample of a normal map, if you still need more samples, let me know:

[http://www98.zippyshare.com/v/v2MAxKr1/file.html](http://www98.zippyshare.com/v/v2MAxKr1/file.html)
