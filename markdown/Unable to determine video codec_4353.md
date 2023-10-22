## Post #1
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2010-04-19T12:16:22+00:00
- Post Title: Unable to determine video codec

I have this file from the production of a game in 1997 (it does not actually appear in the game in this format, this is before it was compressed and included in the actual game), it is most likely an uncompressed video. This video does not play on my system for some reason (and I have a lot of codecs installed). Does it file play on anyone else's system? If so, what codec/program did you use?

[http://www.thezorklibrary.com/history/t ... rBlood.mov](http://www.thezorklibrary.com/history/tzlguest/From_ScottG/Movies/Altar/AltarBlood.mov)


Thanks,
Andy
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-05-16T08:05:39+00:00
- Post Title: Unable to determine video codec

The file itself has a QuickTime header, the movie doesnt play for me, i did scan it by hand though, and the frames are in there, uncompressed bitmaps. 
So, technically, there is not really a codec! =D
## Post #3
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2010-05-17T03:50:54+00:00
- Post Title: Unable to determine video codec

Its a QuickTime file missing the moov atom.
It is possible that the file was stored with the moov atom in a resource fork as per here
[http://clone2727.blogspot.com/2010/04/q ... forks.html](http://clone2727.blogspot.com/2010/04/quicktime-resource-forks.html) and at some point the resource fork (and moov atom) were lost.
