## Post #1
- Username: mrjaredbeta
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 26, 2011 2:34 am
- Post datetime: 2012-09-30T23:17:39+00:00
- Post Title: Pac Man World 2 PS2 Music Interleave Problem

Hey, I haven't been here for a while but I have a problem. I have tried to extract and convert the music from PMW2 for PS2 but I've been having trouble. I've found that each music track is a desperate file right on the disc and the format is .mus

I've put the audio into MFAudio and it plays, but it plays with a slight stutter and I cannot convert it (it hangs). I opened Cube Media Player and I changed it from PCM to ADPCM and it plays but I guess I need to find the correct interleave. I tried all the presets but they don't work, how do you find the interleave through hex?
## Post #2
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2012-10-01T22:25:35+00:00
- Post Title: Pac Man World 2 PS2 Music Interleave Problem

Try the vgmstream plugin (be sure to read the readme for proper setup).

If that doesn't work, I made a quick tutorial on how to get PS2 ADPCM interleave here: [viewtopic.php?f=17&t=8460&p=68454#p68454](http://forum.xentax.com/viewtopic.php?f=17&t=8460&p=68454#p68454)
## Post #3
- Username: mrjaredbeta
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 26, 2011 2:34 am
- Post datetime: 2012-10-01T23:29:43+00:00
- Post Title: Pac Man World 2 PS2 Music Interleave Problem

I actually just found out how to work it a couple hours ago. Here's what I did:

First, I'm glad that the music files are separated into tracks right on the disc, cause scanning it with Cube Media Player didn't show up with any of them.

So, I loaded up the track called "GHOST4.MUS" in CMP and I did what I usually do: Change PCM to ADPCM, 48000Hz to 44100Hz, and I actually found a good interleave but it isn't exactly the right one. He is the sample product of that: [http://www.mediafire.com/?cw1uv6lbckxsnfg](http://www.mediafire.com/?cw1uv6lbckxsnfg)

I was mad cause I couldn't find a way to get rid of the stutter, so I quit for the night. I was sitting at school and I was thinking about hex editing and I came home and looked at the file in HxD. First I noticed that there was 4800 bytes of 0s, even though that was not the interleave. I then thought of something, I deleted every set of those 0s and then it seemed like the pausing stopped. I went back to change the full settings in CMP: Set PCM to ADPCM, 48000Hz to 44100Hz, but then I found the exact interweave (16400, I kinda guessed and it just turned out to be that!). Anyways, here is the final product sample: [http://www.mediafire.com/?pm4vrrav99r1z0x](http://www.mediafire.com/?pm4vrrav99r1z0x)

You can here little crackling where the pauses used to be, but barely and sometimes it is not noticeable at all. This is great, cause no OST of this game was released and I think this is the best possible quality (unless the PC is or someone extracted it from the GC version). I love the soundtrack in this game, it is very original and awesome, should be appreciated more than it is.
## Post #4
- Username: mrjaredbeta
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 26, 2011 2:34 am
- Post datetime: 2012-10-01T23:38:59+00:00
- Post Title: Pac Man World 2 PS2 Music Interleave Problem

I actually just found out how to work it a couple hours ago. Here's what I did:

First, I'm glad that the music files are separated into tracks right on the disc, cause scanning it with Cube Media Player didn't show up with any of them.

So, I loaded up the track called "GHOST4.MUS" in CMP and I did what I usually do: Change PCM to ADPCM, 48000Hz to 44100Hz, and I actually found a good interleave but it isn't exactly the right one. He is the sample product of that: [http://www.mediafire.com/?cw1uv6lbckxsnfg](http://www.mediafire.com/?cw1uv6lbckxsnfg)

I was mad cause I couldn't find a way to get rid of the stutter, so I quit for the night. I was sitting at school and I was thinking about hex editing and I came home and looked at the file in HxD. First I noticed that there was 4800 bytes of 0s, even though that was not the interleave. I then thought of something, I deleted every set of those 0s and then it seemed like the pausing stopped. I went back to change the full settings in CMP: Set PCM to ADPCM, 48000Hz to 44100Hz, but then I found the exact interweave (16400, I kinda guessed and it just turned out to be that!). Anyways, here is the final product sample: [http://www.mediafire.com/?pm4vrrav99r1z0x](http://www.mediafire.com/?pm4vrrav99r1z0x)

You can here little crackling where the pauses used to be, but barely and sometimes it is not noticeable at all. This is great, cause no OST of this game was released and I think this is the best possible quality (unless the PC is or someone extracted it from the GC version). I love the soundtrack in this game, it is very original and awesome, should be appreciated more than it is.
