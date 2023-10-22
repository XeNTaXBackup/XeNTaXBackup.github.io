## Post #1
- Username: mikehood
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Jun 20, 2006 1:45 pm
- Post datetime: 2008-05-17T09:43:04+00:00
- Post Title: :(  Stranglehold sound

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-05-28T20:26:34+00:00
- Post Title: :(  Stranglehold sound

Yes ive been looking to extract the music for this game. help?
## Post #3
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-01T22:03:01+00:00
- Post Title: :(  Stranglehold sound

I would like to help. That file that you posted is just raw PCM. There seem to be errors in it, though. Those parts where you hear static is just where one byte was added or removed, messing up the 2-byte boundries of 16-bit PCM. That might be a little bit confusing, so just look at this image:



I add one byte to the beginning of the file, so that all the bytes would be shifted. You can see that where there is static in one file, there is recognizable audio in the other, and vice versa.

The only thing that I can think of that this has come from is either errors, headers in the PCM data, or a lookup table somewhere else that tells how to interpret the data.
