## Post #1
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2007-06-13T22:10:43+00:00
- Post Title: compressed rtx file

I have a few friends tryng to work on this but have been having no luck. maybe one of you guys can help. Jasmine said it must be an alternate zlib compression. Any help would be really appreciated. this is for smackdown vs raw 07 on the ps2.
[Svr2007_RTX.zip](https://xentaxbackup.github.io/file/1214_Svr2007_RTX.zip)
## Post #2
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2007-06-14T04:35:11+00:00
- Post Title: compressed rtx file

Even though it appears to have a "zlib type" header code, I believe that I am mistaken.  I believe this is not zlib and I do not know what type of compression/encryption that it may be using.  Any help would be appreciated.
## Post #3
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2007-06-29T20:26:41+00:00
- Post Title: compressed rtx file

this still is unsolved anyone else that can shed some light please do.
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-01T21:47:36+00:00
- Post Title: compressed rtx file

You could try to open the exe file in a hex editor and look for something that indicates a compression technique (e.g. "zlib" etc)
## Post #5
- Username: juskrey
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 01, 2008 5:50 pm
- Post datetime: 2008-04-01T11:53:54+00:00
- Post Title: compressed rtx file

It is definetly NOT zlib or deflate.
It looks like some custom LZ compression, probably with huffman encoding.
