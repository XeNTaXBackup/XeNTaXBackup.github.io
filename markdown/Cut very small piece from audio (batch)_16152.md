## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2017-04-16T16:46:44+00:00
- Post Title: Cut very small piece from audio (batch)

I has several hundred wav files, which has pitch noise in the very beginning and he very short: over 0,0005-0,0010 milliseconds - [http://i.imgur.com/6UqLgkH.png](http://i.imgur.com/6UqLgkH.png)

ffmpeg on windows could cut over 0.01, not 0.0005.

Could be simple utility, which could cut 0,0005-0,0010 milliseconds of audio in very beginning as single and many from batch?

Be glad for help.

Few example samples - [http://dropmefiles.com/Blknu](http://dropmefiles.com/Blknu)
## Post #2
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2017-04-30T07:00:15+00:00
- Post Title: Cut very small piece from audio (batch)

0.0005-0.0010 could be trimmed with sox:

```
sox input output trim 0.0005
```
