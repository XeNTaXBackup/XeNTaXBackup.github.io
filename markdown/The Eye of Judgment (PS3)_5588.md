## Post #1
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-12-20T02:59:59+00:00
- Post Title: The Eye of Judgment (PS3)

This game uses some kind of ADPCM variant for everything that's not BGM.

I know the music in the BGM folder (not BGM_6 - I just hear static from anything in this folder) is PS2 ADPCM @ 48kHz / 0x10 interleave.

Can anyone write me a script so I can at least playback the rest of the audio files in Sound Forge or convert them to WAV using VGMstream?

[http://www.flameupload.com/files/1NQMYZUQ/Sound.rar](http://www.flameupload.com/files/1NQMYZUQ/Sound.rar)
## Post #2
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2010-12-22T16:33:51+00:00
- Post Title: The Eye of Judgment (PS3)

Oh these are PS ADPCM. I added support for these to vgmstream a long time ago. I just need to fix a few things now that you uploaded these to support a new header variation (something in the SGH file) and a new layout for the data to play correctly.
## Post #3
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-12-23T02:18:42+00:00
- Post Title: The Eye of Judgment (PS3)

Thanks a lot bxaimc.

I never can say thanks enough for the extremely useful and awesome tool known as VGMstream 

EDIT: Can you let me know when you've put up the new build of VGMstream with the support?
