## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2011-12-30T05:32:52+00:00
- Post Title: Assassin's Creed Recollection (iPhone) *.caf audio

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2011-12-30T21:23:17+00:00
- Post Title: Assassin's Creed Recollection (iPhone) *.caf audio

AAC 22050Hz stereo 96kbps
FFmpeg can decode.
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2011-12-31T07:30:26+00:00
- Post Title: Assassin's Creed Recollection (iPhone) *.caf audio

Thanks for your answer. I've found out about AAC LC already.
However I don't use FFmpeg and search for a way to manipulate the header to standard AAC so that all Windows players can play these files and I can import it to Audition or WaveLab. Can FFMpeg export the files with a different header and leave the data intact?
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-12-31T12:57:20+00:00
- Post Title: Assassin's Creed Recollection (iPhone) *.caf audio

probably, try -acodec copy and whatever output extension you want
