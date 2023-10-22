## Post #1
- Username: Franco
- Rank: beginner
- Number of posts: 37
- Joined date: Sat May 28, 2022 7:03 am
- Post datetime: 2022-08-23T11:34:29+00:00
- Post Title: LEGO Games FONT ?

Hello, the general FONT files of LEGO games are in FT2 format.
For example, this file belongs to the LEGO Star Wars: The Skywalker Saga game.
How can I open and edit this FONT file, can you help?
[FONT_SUBTITLE_NXG.rar](https://xentaxbackup.github.io/file/22682_FONT_SUBTITLE_NXG.rar)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-23T18:28:12+00:00
- Post Title: LEGO Games FONT ?

Hi, here's file format [http://wiki.xentax.com/index.php/LEGO_Games_FT2](http://wiki.xentax.com/index.php/LEGO_Games_FT2)

And here is script to unpack/pack DDS image [https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/LEGO%20Games/LEGO_Games_FT2_script.bms)

You can use it with quickbms [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
## Post #3
- Username: Franco
- Rank: beginner
- Number of posts: 37
- Joined date: Sat May 28, 2022 7:03 am
- Post datetime: 2022-08-23T20:52:36+00:00
- Post Title: LEGO Games FONT ?

Thank you very much, this works. I edited and repackaged the FONT file, but there is a size problem when importing it into the main archive .DAT file. So it doesn't import. How can I overcome this, what should I do?
[1.jpg](https://xentaxbackup.github.io/file/22683_1.jpg)
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-24T18:08:33+00:00
- Post Title: LEGO Games FONT ?

There are two solutions:

First is to make sure that new font will be smaller or equal original font. 
I mean here new compressed size should be less than 4419 for your case.

Second solution is to try all reimport modes in quickbms. Some of them allow
new file to be bigger than original
More info here [http://aluigi.zenhax.com/papers/quickbms.txt](http://aluigi.zenhax.com/papers/quickbms.txt)
and here [https://www.google.com/search?client=fi ... n+original](https://www.google.com/search?client=firefox-b-d&q=quickbms+how+to+reimport+bigger+than+original)
## Post #5
- Username: Franco
- Rank: beginner
- Number of posts: 37
- Joined date: Sat May 28, 2022 7:03 am
- Post datetime: 2022-08-24T19:24:52+00:00
- Post Title: LEGO Games FONT ?

> Reply from ikskoks ↑Thu Aug 25, 2022 2:08 am at Thu Aug 25, 2022 2:08 am
>
> 
There are two solutions:

First is to make sure that new font will be smaller or equal original font. 
I mean here new compressed size should be less than 4419 for your case.

Second solution is to try all reimport modes in quickbms. Some of them allow
new file to be bigger than original
More info here http://aluigi.zenhax.com/papers/quickbms.txt
and here https://www.google.com/search?client=fi ... n+original

Thank you. I made a trial by importing the original file of the game and got the same error.
I guess it has nothing to do with editing the FONT file.
Because re-importing the original file also gives the same error and no import mode works.
What else would you suggest and what should I do
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-24T20:18:31+00:00
- Post Title: LEGO Games FONT ?

Well, you could always try to find a better compressor (or create one) and then create a tool that uses it.
Or eve better - create a tool that can overcome file size limits.
But it is more advanced hacking, so you need a lot of programming and reverse engineering knowledge to do it.
Here is a good starting point [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
## Post #7
- Username: Franco
- Rank: beginner
- Number of posts: 37
- Joined date: Sat May 28, 2022 7:03 am
- Post datetime: 2022-08-24T20:28:19+00:00
- Post Title: LEGO Games FONT ?

> Reply from ikskoks ↑Thu Aug 25, 2022 4:18 am at Thu Aug 25, 2022 4:18 am
>
> 
Well, you could always try to find a better compressor (or create one) and then create a tool that uses it.
Or eve better - create a tool that can overcome file size limits.
But it is more advanced hacking, so you need a lot of programming and reverse engineering knowledge to do it.
Here is a good starting point viewtopic.php?f=29&t=22266

Thank you for your interest and help. But I don't know that much, so I guess I don't have enough experience to do that.
My only hope is for someone to create an import argument
