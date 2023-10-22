## Post #1
- Username: nickcollison
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Oct 27, 2009 12:45 pm
- Post datetime: 2010-10-19T11:52:08+00:00
- Post Title: NBA 2k11 audio .bin files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: JaoSming
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 20, 2011 3:33 am
- Post datetime: 2011-01-19T19:35:27+00:00
- Post Title: NBA 2k11 audio .bin files

I'd like to bump this.  The fact that we were able to crack it in 2k9 but not in 2k10 or 2k11 is really annoying.

If anyone could help us out it would be greatly appreciated.
## Post #3
- Username: PDub
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 20, 2011 6:51 am
- Post datetime: 2011-01-19T23:36:58+00:00
- Post Title: NBA 2k11 audio .bin files

The file(s) seems to be back to back compressed audio with 4kb parts, with the last 1058 bytes nothing but "AA" padding.  Each header starts with 69A1BED202000000CF05000002000000
2256  -  It's different for each part after this.  That is the sample rate (5622 or 22050).  The 02 after 69A1BED2 appears to be the channels, as files that should be speech files have an 01, indicating that it is mono.  

I believe it is a native format to Windows, since the game required a few Microsoft redistributable files to be installed.

Here is an attached file.  It should be a crowd yelling "airball!" If anyone can figure it out.
[cairball.rar](https://xentaxbackup.github.io/file/3821_cairball.rar)
