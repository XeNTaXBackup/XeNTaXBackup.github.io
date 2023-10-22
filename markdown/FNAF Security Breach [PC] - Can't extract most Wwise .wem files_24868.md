## Post #1
- Username: Voldemort127
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 06, 2018 11:26 pm
- Post datetime: 2021-12-21T05:27:59+00:00
- Post Title: FNAF: Security Breach [PC] - Can't extract most Wwise .wem files

I've decrypted the game's .pak file and I found the WwiseAudio folder with all the sound files and wwise metadata in it. I can export some .wem files in General.bnk with "WwiteAudio Extracter" ([https://www.gildor.org/smf/index.php?ac ... ttach=2015](https://www.gildor.org/smf/index.php?action=dlattach;topic=7596.0;attach=2015)), but they are mostly just short sound effects, or ambient drone sounds. The rest give the classic "expected 0x42 fmt if vorb missing" error with most tools. I'm mainly interested in the actual music files.

Surely there must be some metadata somewhere about the audio format in the .wem files, otherwise how does Unreal Engine 4 know how to play them?

Here's the full WwiseAudio folder from the decrypted Content folder of the game: 
[https://mega.nz/file/VtpWyaZS#pbWPT1dvb ... d_qpewznf4](https://mega.nz/file/VtpWyaZS#pbWPT1dvbKN1ZG8zue-EX0HM8KbgMABIWd_qpewznf4)

P.S. I'm not asking you to do the extraction for me. Just give me a method that works for all .bnk and .wem files in the archive, I'll do the rest.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2021-12-21T16:41:26+00:00
- Post Title: FNAF: Security Breach [PC] - Can't extract most Wwise .wem files

These files are ADPCM, not vorbis.

Download the latest version of [vgmstream](https://vgmstream.org/downloads) as it can play these .wem / .bnk files without issue.

It's probably also worth checking out [bnnm's Wwiser](https://github.com/bnnm/wwiser/releases) which can get the original names of the audio files as well.
