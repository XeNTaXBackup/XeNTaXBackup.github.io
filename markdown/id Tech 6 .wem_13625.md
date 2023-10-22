## Post #1
- Username: Koma
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Nov 07, 2014 8:59 pm
- Post datetime: 2015-12-05T20:53:52+00:00
- Post Title: id Tech 6 .wem

Greetings.
So this is how things look like, I have extracted everything from the .bnk databases but the extracted files are giving me a big headache.
The audio files are .wem's, but I haven't managed to convert them with conventional methods.
Here are a few samples - [https://mega.nz/#!uE01VbgB!_V6MzjpH3SsB ... VStrGLgr3g](https://mega.nz/#!uE01VbgB!_V6MzjpH3SsBIm2f0LsRiBZ6vV7PmVbrNVStrGLgr3g)

The traditional conversion method resulted in this error (which also says that the files probably aren't in vorbis but maybe in something else, like little-endian 16-bit PCM):

```
Audiokinetic Wwise RIFF/RIFX Vorbis to Ogg Vorbis converter 0.22 by hcs

Input: 4581.wem
Parse error: expected 0x42 fmt if vorb missing
```

Tried to open this as raw data in Audacity too but to no avail.
Any assistance with this issue will be appreciated
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-12-05T21:14:49+00:00
- Post Title: id Tech 6 .wem

WWise ADPCM

This should do it.
[wwise_ima_adpcm.rar](https://xentaxbackup.github.io/file/10107_wwise_ima_adpcm.rar)
## Post #3
- Username: Koma
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Nov 07, 2014 8:59 pm
- Post datetime: 2015-12-05T21:19:25+00:00
- Post Title: id Tech 6 .wem

Beautiful. Thanks a ton.
