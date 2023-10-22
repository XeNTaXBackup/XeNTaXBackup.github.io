## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-05-08T21:12:01+00:00
- Post Title: Darksiders multichannel XMA

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-05-08T22:28:35+00:00
- Post Title: Darksiders multichannel XMA

This is 32khz stereo, it won't decode properly with the more common 48khz stereo you're probably using. Change 80 BB (0xBB80, 48000 Hz) to 00 7D (0x7D00, 32000) in the header.

You're right that there are two streams (each two channels), one at 0 and one at 800.
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-05-09T01:42:51+00:00
- Post Title: Darksiders multichannel XMA

Thanks, I changed the sample rate in the header and it worked but I don't know why. 
Why isn't the sample rate indifferent to toWAV? I thought that's basically just the sample rate of the output wave file, but apparently I'm wrong. Maybe you could explain this? Thanks.
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-05-09T04:24:53+00:00
- Post Title: Darksiders multichannel XMA

Nope, the internal structure of the frames is different.  There's more or less frequency range involved, and with the frequency known ahead of time you don't have to waste space in the stream saying this over and over.  Same thing with mono vs stereo.  I don't have any details on the internal structure of the frames, but this seems to be the case.
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-05-09T12:20:21+00:00
- Post Title: Darksiders multichannel XMA

Thanks HCS, that cleared up some things.
