## Post #1
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-02-03T08:22:05+00:00
- Post Title: Captain Claw FEC file

Hi guys. 

I'm looking someone to help me extract videos in .smk format from CLAW.FEC file and pack them again.
It is possible to extract videos from FEC using FMV-Extractor or X-Ripper but I would like also replace videos with others.
Any ideas?

Link to CLAW.FEC file:

[http://www.mediafire.com/file/9yfncm88b ... W.FEC/file](http://www.mediafire.com/file/9yfncm88b9pjewk/CLAW.FEC/file)
## Post #2
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-02-10T14:09:05+00:00
- Post Title: Captain Claw FEC file

I fgiured out how to replace videos. It is very simple.  

First, empty FEC file is only 15 Bytes, 12-th Byte define how many videos will be played in game (max 12 videos).

Secondly, before every movie there are some Bytes but I don't know what is their meaning (first Byte in these Bytes = number of movie, but I noticed it can be random?).

Thirdly, every movie is a .smk movie (magic numbers SMK2 - 53 4D 4B 32) and it is possible to replace but you have to use old RADTools app to convert .avi to .smk. Videos in game can have max res 640x480.

So, in every Monolith game where there is FEC file it shoud be possible to replace movies!
## Post #3
- Username: AbooAshraf
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 21, 2021 1:26 am
- Post datetime: 2021-09-20T17:36:06+00:00
- Post Title: Captain Claw FEC file

i still don't understand how to replace videos in the FEC file !
help please
