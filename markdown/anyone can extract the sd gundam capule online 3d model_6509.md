## Post #1
- Username: jerrygoh89
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 26, 2011 8:15 pm
- Post datetime: 2011-04-26T13:53:37+00:00
- Post Title: anyone can extract the sd gundam capule online 3d model

anyone can extract the sd gundam capule online 3d model
## Post #2
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-04-26T15:44:48+00:00
- Post Title: anyone can extract the sd gundam capule online 3d model

here[viewtopic.php?f=10&t=3374](http://forum.xentax.com/viewtopic.php?f=10&t=3374)
## Post #3
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-02-16T16:13:16+00:00
- Post Title: anyone can extract the sd gundam capule online 3d model

> Reply from dj082502
>
> hereviewtopic.php?f=10&t=3374
Thank you for your last help.
Do you know how to convert mod to obj?
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-16T16:38:50+00:00
- Post Title: anyone can extract the sd gundam capule online 3d model

Looks like aluigi posted an unpacker that gets the filenames.
Is this the output from that one? [viewtopic.php?p=28471#p28471](http://forum.xentax.com/viewtopic.php?p=28471#p28471)

There's a lot of stuff stored in this format, like bone names, and some other stuff after the mesh section.

Header has 4 integers that will be of interest.
Vertex and index buffers are there.
Uses "unicode" strings.
All strings are 128 bytes long (so in unicode, 256 bytes)

Textures are stored in ".txr" files, and chrrox says they're just tga files.

If there are specs or existing tools that would be useful to know about as well.
