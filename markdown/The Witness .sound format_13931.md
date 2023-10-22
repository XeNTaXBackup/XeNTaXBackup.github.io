## Post #1
- Username: yoyodaman234
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 21, 2012 3:10 pm
- Post datetime: 2016-02-06T11:58:36+00:00
- Post Title: The Witness .sound format

The Witness comes with these .sound files. They appear to be WAV/OGG files with a seemingly random amount of data inserted before and after. I'm not adept enough with coding to try and extract them, so could someone quickly take a look at these?

Sample files: [https://drive.google.com/open?id=0B9_gX ... Ul2VGt3UkU](https://drive.google.com/open?id=0B9_gX1xgvaJ2QnV1dUl2VGt3UkU)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-07T16:38:46+00:00
- Post Title: The Witness .sound format

Quick look for you. Some files are compressed.

The first bytes tell you if the file is compressed or not, and the uncompressed size.
## Post #3
- Username: iamapersontoo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 06, 2019 8:58 pm
- Post datetime: 2019-04-06T13:03:09+00:00
- Post Title: The Witness .sound format

Very, Very late. But I found out that some of the audio files (most likely the wav uncompressed ones) can be opened with audacity. The other ones just give me the not recognized error. The files that error have the file headers that hint to ogg compressed files (i.e libVorbis.)
