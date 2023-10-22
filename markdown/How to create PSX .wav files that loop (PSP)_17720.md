## Post #1
- Username: wad11656
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 19, 2018 5:40 pm
- Post datetime: 2018-02-19T10:15:29+00:00
- Post Title: How to create PSX .wav files that loop? (PSP)

I've been working all day on trying to help a Reddit poster create his own .wav music files for "Spongebob: Truth or Square" (PSP) that correctly loop in-game. ([Here's the Reddit post.](https://www.reddit.com/r/PSP/comments/7ycv3z/need_help_with_replacing_game_music_for_a_psp/)) He was able to find software called [>MFAudio<](https://www.zophar.net/utilities/ps2util/mfaudio-1-1.html) that correctly converted his own audio files to .wav files with the correct ADPCM_PSX codec, as seen below.



The audio plays correctly, but does not loop. I looked into creating looping .wav files. [>I found a video that showed 2 methods to create a looping .wav file using an app<](https://www.youtube.com/watch?v=1ly1KOhiQu0) called [>Wavosaur<](https://www.wavosaur.com/download.php).

However, Wavosaur can't save .wav files with the ADPCM_PSX codec that the PSP game uses. So, after saving my modified .wav in Wavosaur, I convert the .wav into the PSP .wav format with MFAudio. I think this conversion may make it lose the loop markers(?) Or perhaps looping was coded into .wav files completely differently for PSP games.

Perhaps there are clues in the hex of the original, looping .wav files. I attached one of these files for reference.

Can I manually hex-edit in the loop data into the .wav file?

I'd really appreciate any help!
[spongebob_square_orignal_wav.zip](https://xentaxbackup.github.io/file/13931_spongebob_square_orignal_wav.zip)
