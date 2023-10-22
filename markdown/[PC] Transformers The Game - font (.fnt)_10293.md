## Post #1
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-04-02T19:29:52+00:00
- Post Title: [PC] Transformers: The Game - font (.fnt)

Hi, guys 

My friend need help with editing fonts in this game. There are a few files with extension .dds and .fnt

Editing DDS file in Gimp don't resolve the problem (the game doesn't see changed DDS textures) and I think that he need good FNT editor (but normal fnt editors used to edit windows fnt files like Raster Font Editor, Fony, Sib Font editor doesn't work).

Can someone look at these files and tell me how can i edit them? Do you know working .fnt editor?
[Transformers fonts.rar](https://xentaxbackup.github.io/file/6305_Transformers fonts.rar)
## Post #2
- Username: Rjack
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 14, 2012 4:53 pm
- Post datetime: 2013-04-03T11:01:08+00:00
- Post Title: [PC] Transformers: The Game - font (.fnt)

I think the fnt is freetype 1.x
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-04-03T14:48:38+00:00
- Post Title: [PC] Transformers: The Game - font (.fnt)

Thank you 

Is it possible to edit this freetype font?
## Post #4
- Username: Rjack
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 14, 2012 4:53 pm
- Post datetime: 2013-04-03T16:51:49+00:00
- Post Title: [PC] Transformers: The Game - font (.fnt)

I don't know any coding thing at all.
Maybe you can find something useful at the offical website. [http://www.freetype.org/freetype1/](http://www.freetype.org/freetype1/)
## Post #5
- Username: mix
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 16, 2008 2:14 am
- Post datetime: 2013-07-13T14:24:12+00:00
- Post Title: [PC] Transformers: The Game - font (.fnt)

Inside those .fnt files there are the original .dds files which you need to edit and put back. It's easiest with hex editor, just copy everything from "DDS" to last few bytes.
## Post #6
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-07-14T00:55:27+00:00
- Post Title: [PC] Transformers: The Game - font (.fnt)

Just don't touch last 0x30 bytes its not texture and if you change this, game may be not working
