## Post #1
- Username: DeathChaos
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 01, 2017 2:27 pm
- Post datetime: 2019-11-01T13:22:03+00:00
- Post Title: RE6 Switch Audio Format

Hello.

I seem to be unable to figure out what audio format is being used for the Switch version of RE6, I figured it'd be common formats like bfwav/bfstm or something like libopus, but I seem to be unable to figure out what they are, and the file header doesnt seem to have any identifiable magic either.

[Here are some sample arc files that contain voices, arc format seems to be same as PC version](https://cdn.discordapp.com/attachments/377899265424621569/639815437818789898/RE6_Switch_VoiceArcSample.7z)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-11-03T00:09:46+00:00
- Post Title: RE6 Switch Audio Format

Once the files in the archive are decompressed (zlib compression), the audio is in GameCube DSP 4-bit ADPCM format.  The files all seem to be mono, so you have the coefficients at offset 0x18 and the audio data at 0x80.  The sample rate is at 0x64.  The coefficient type is Normal (Little Endian).

Hope that helps!
## Post #3
- Username: DeathChaos
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 01, 2017 2:27 pm
- Post datetime: 2019-11-04T20:55:55+00:00
- Post Title: RE6 Switch Audio Format

This does indeed help, was able to extract/convert audio, thanks for the info!

Edit: When reading them with tools such as vgmstream on foobar the pitch seems accelerated, and tools such as [VGAudio](https://github.com/Thealexbarney/VGAudio) seem to have some problems with it, any idea why this might be?
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-11-05T00:09:25+00:00
- Post Title: RE6 Switch Audio Format

It seems the sample rate of 48,000 in the files is too fast.  32,000 should probably be the right value for all of the sounds.  There are some values in the file table in the .arc file  - seems to be 0x597BC479 for most files.  This info might be some flags about the audio data, including the correct sample rate.

I think VGAudio might have some issues as it doesn't seem like the files are in a known format, i.e. they don't have the same header format as normal DSP files.
