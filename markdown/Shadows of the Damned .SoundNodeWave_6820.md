## Post #1
- Username: ma3x666
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Nov 13, 2010 10:49 pm
- Post datetime: 2011-06-20T11:09:08+00:00
- Post Title: Shadows of the Damned .SoundNodeWave

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: RedDeadRedemption
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jul 13, 2010 10:23 pm
- Post datetime: 2011-06-21T07:21:15+00:00
- Post Title: Shadows of the Damned .SoundNodeWave

Probabely it's just a OGG file.
To extract sounds from xxx files, use [umodel](http://www.gildor.org/downloads) with -export -sounds options.
## Post #3
- Username: ma3x666
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Nov 13, 2010 10:49 pm
- Post datetime: 2011-06-21T11:07:22+00:00
- Post Title: Shadows of the Damned .SoundNodeWave

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-06-21T21:08:50+00:00
- Post Title: Shadows of the Damned .SoundNodeWave

if its 360 then the audio is xma. need to ad an xma header and convert with towav.
## Post #5
- Username: ma3x666
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Nov 13, 2010 10:49 pm
- Post datetime: 2011-06-22T05:58:24+00:00
- Post Title: Shadows of the Damned .SoundNodeWave

And where do i put xma header? after first 20 bit or 30 or in the beginning?
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-06-22T16:49:18+00:00
- Post Title: Shadows of the Damned .SoundNodeWave

The XMA start stream usually has a flag thats FC01C001 so you count back 6 bytes and thats xma start stream after the junk header the soundnodewave has.

example of a start stream is 280001000BEDFC01C001 so put it before the 28, numbers may vary in each xma track but the pattern is the same.
## Post #7
- Username: ma3x666
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Nov 13, 2010 10:49 pm
- Post datetime: 2011-06-23T09:14:05+00:00
- Post Title: Shadows of the Damned .SoundNodeWave

Well, there's no FC01C001 flag in this file.
