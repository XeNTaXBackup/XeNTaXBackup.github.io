## Post #1
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2016-09-23T17:57:15+00:00
- Post Title: Change File Header

I'm looking to change the frequency of a file from 32000 HZ to 48000. How can I change this, using HxD? This was started in another thread, but I thought this would do better on its own.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-09-23T20:09:38+00:00
- Post Title: Change File Header

Look for "7D 00" or "00 7D"

If 7D 00 change it to BB 80
If 00 7D change it to 80 BB
## Post #3
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2016-09-23T20:35:42+00:00
- Post Title: Change File Header

I was afraid of this. It won't play now. Is there something else? Cause if not, it just won't work.
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-09-24T03:05:23+00:00
- Post Title: Change File Header

Upload the original file
## Post #5
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-09-24T05:32:36+00:00
- Post Title: Change File Header

Only do this if the audio sounds like it is running too slow, otherwise just changing the sample rate is going to speed it up, but it won't fix your quality problem.
## Post #6
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-09-24T05:58:38+00:00
- Post Title: Change File Header

Yes, I mentioned that in the other thread as well. Increasing the sample rate will just speed up the audio file, not increase it's fidelity.
