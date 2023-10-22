## Post #1
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-01-31T20:11:13+00:00
- Post Title: FMOD SoundBank v4 Interactive MP3

I'm having a lot of trouble splitting up interactive MP3s from the game Strike Suit Zero, which uses FSB4 to store all of its sound. I've managed to extract every other MP3 sample, but with this type it never sounds right.

The sample in question is 6 channels at 44100Hz. FMOD stores each frame with weird alignment, where the frames seem either 2, 4, or 16 byte aligned. I'm trying to split the file up into three so it can be played (from what I can tell, MP3s usually have a 2 channel limit unless it's one of those extended ones), but I have no idea how to split it up properly. I'm currently calculating the length of each frame, then appending it to a file. The big problem right now is I'm encountering invalid headers or otherwise invalid frames. Could someone take a look and tell me how everything's divided up?

I use this code to get frame length: [http://www.hydrogenaudio.org/forums/ind ... t&p=747716](http://www.hydrogenaudio.org/forums/index.php?showtopic=85125&view=findpost&p=747716)

Trying to listen in foobar2000 produces junk, and loading it in Audacity produces one track with a lot of random clicks and squeaks, with sections of noise.

The sample header is included. See [http://www.fmod.org/forum/viewtopic.php?t=1551](http://www.fmod.org/forum/viewtopic.php?t=1551) for format.

[http://www.mediafire.com/file/xcz89bx6x ... sample.zip](http://www.mediafire.com/file/xcz89bx6xcob0z9/fsb_sample.zip) (File is large, uploaded to MediaFire.)
## Post #2
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-02-02T17:52:55+00:00
- Post Title: FMOD SoundBank v4 Interactive MP3

Never mind, I got it. The frames are 16 byte aligned, and my code didn't get the alignment correct.
