## Post #1
- Username: Harime Nui
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Oct 11, 2014 7:32 am
- Post datetime: 2015-10-18T20:36:48+00:00
- Post Title: Witcher 3 save files

I am trying to unpack and pack a Witcher 3 savefile, which is a archive containing multiple files. 
Unpacking works pretty well, but with packing I have problems, because there seems to be a checksum which needs to be recalculated.
I tried several different algorithms, like adler and crc, but I just can't figure it out.
Maybe someone knows more about it?
## Post #2
- Username: RedEyeX32
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 22, 2014 4:38 am
- Post datetime: 2015-10-28T16:10:28+00:00
- Post Title: Witcher 3 save files

The internal files seems to be compressed, I cannot see a checksum.
## Post #3
- Username: Harime Nui
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Oct 11, 2014 7:32 am
- Post datetime: 2015-10-31T21:51:12+00:00
- Post Title: Witcher 3 save files

Yes, my assumption with the checksum was wrong, it is just the file length in byte of the uncompressed file. It is also not an archive which holds multiple files, but it is one file which gets split into 1048576 byte long parts. Every part then gets compressed with lz4 ([https://code.google.com/p/lz4/](https://code.google.com/p/lz4/)).
I was actually able to "unpack" and "pack" a savefile, but i was not able to change much jet, the game breaks very easy:



The header of a Witcher 3 save file. game_breaks.jpg (75.83 KiB) Viewed 214 times



Edit:
Here is a image how the header of the savefile looks like:
## Post #4
- Username: RedEyeX32
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 22, 2014 4:38 am
- Post datetime: 2015-11-01T00:44:05+00:00
- Post Title: Witcher 3 save files

> Reply from Harime Nui
>
> Yes, my assumption with the checksum was wrong, it is just the file length in byte of the uncompressed file. It is also not an archive which holds multiple files, but it is one file which gets split into 1048576 byte long parts. Every part then gets compressed with lz4 (https://code.google.com/p/lz4/).
I was actually able to "unpack" and "pack" a savefile, but i was not able to change much jet, the game breaks very easy:
game_breaks.jpg

Edit:
Here is a image how the header of the savefile looks like:

I was assuming that it was using LZO1X, but if it works, good job!
## Post #5
- Username: Harime Nui
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Oct 11, 2014 7:32 am
- Post datetime: 2015-11-01T09:05:25+00:00
- Post Title: Witcher 3 save files

> Reply from RedEyeX32
>
> I was assuming that it was using LZO1X, but if it works, good job!

I just used this [https://github.com/Cyan4973/lz4/releases/tag/r131](https://github.com/Cyan4973/lz4/releases/tag/r131) library on every part for uncompressing and compressing on default settings, and it worked without any problems. As far as I can see it calls itself LZ4, but there are so many of them it could be a modified version of LZO1X. 
I think on it's base it is called Lempel-Ziv-Welch Compression: [https://www.youtube.com/watch?v=Jqc418tQDkg](https://www.youtube.com/watch?v=Jqc418tQDkg)
## Post #6
- Username: Harime Nui
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Oct 11, 2014 7:32 am
- Post datetime: 2015-11-12T19:53:20+00:00
- Post Title: Witcher 3 save files

Still trying to figure out the save file itself. To me it looks like some kind of binary XML file?

Maybe someone knows in which file format they are saved?
[decompressedSav.zip](https://xentaxbackup.github.io/file/10001_decompressedSav.zip)
## Post #7
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2016-01-02T15:55:20+00:00
- Post Title: Witcher 3 save files

Nice work Harime Nui.
Although I don't really bring anything interesting and useful to the subject, I'm pretty anxious to see a working save editor.
Unfortunately we didn't see that with TW2, in fact I think that only the XBox360 community seems to have gotten a working editor for TW2, albeit very primitive in that it only allowed to change Money, XP, Upgrade Points, Level.

Anyway, I Googled for a little bit in hope of finding something that might be useful from past projects which never really made it.
I know that the probability of any of this information being useful is close to zero but nonetheless...

Witcher 1 (I know, didn't use REDEngine anyway):
[http://witcher.wikia.com/wiki/KEY_BIF_V1.1_format](http://witcher.wikia.com/wiki/KEY_BIF_V1.1_format)
[http://witcher.wikia.com/wiki/TheWitcherSave_format](http://witcher.wikia.com/wiki/TheWitcherSave_format)

Witcher 2
[https://github.com/13xforever/Witcher-2 ... SaveFormat](https://github.com/13xforever/Witcher-2-Save-Editor/tree/master/SaveFormat)
[https://github.com/yole/Gibbed.RED/tree ... rmats/Save](https://github.com/yole/Gibbed.RED/tree/master/Gibbed.RED.FileFormats/Save)

Witcher 3 (unpacking seems to work too)
[https://github.com/Atvaark/W3SavegameEditor](https://github.com/Atvaark/W3SavegameEditor)


Best of luck, I hope more people join this effort.
## Post #8
- Username: DanRom
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 13, 2016 4:21 pm
- Post datetime: 2016-06-20T18:34:59+00:00
- Post Title: Witcher 3 save files

So, whazzup, folks?
Is there any solution for Witcher 3?
