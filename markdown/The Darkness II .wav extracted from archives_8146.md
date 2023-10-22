## Post #1
- Username: hoodlum47
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jan 30, 2011 6:01 am
- Post datetime: 2012-01-29T14:27:58+00:00
- Post Title: The Darkness II .wav extracted from archives

Hi all, I seriously can't figure these things out, their filesize indicates they are raw PCM data or something similar but they won't play in anything. I even took a look at one of them through a hex editor and it doesn't even seem to have an audio-related header. This is getting me really confused so if someone could look into this example file and help me figure it out, I would be very grateful.

[http://www.mediafire.com/download.php?2cz3r9121drm2mt](http://www.mediafire.com/download.php?2cz3r9121drm2mt)
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-01-29T16:00:45+00:00
- Post Title: The Darkness II .wav extracted from archives

Its Little endian Raw pcm 16bit. Should load just fine in goldwave or audacity.
