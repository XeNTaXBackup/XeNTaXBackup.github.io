## Post #1
- Username: IlDucci
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 20, 2014 10:01 pm
- Post datetime: 2015-05-26T09:34:17+00:00
- Post Title: Alone in the Dark: The New Nightmare ADPCM format

I was checking out the contents of the MIDI folder from this game when I found that, in Dreamcast (And also in PC, although it's unused), the MIDI files contain both PCM samples and ADPCM samples.

Here's a ADPCM sample (With various concadenated audios). It should be at 11025 Hz, 16-bit, 1 channel format. The closest I could get to hear it was playing it with a VOX/OKI ADPCM decoder, but it's not perfect. Anybody knows what is this format?

[http://www.mediafire.com/download/3yr7r ... RTO~.ADPCM](http://www.mediafire.com/download/3yr7r3yrhyxzu1d/DECERTO~.ADPCM)
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-05-26T19:06:57+00:00
- Post Title: Alone in the Dark: The New Nightmare ADPCM format

Looks like it's adpcm_yamaha (pretty common in Dreamcast games apparently):
[http://www55.zippyshare.com/v/9uGomkyK/file.html](http://www55.zippyshare.com/v/9uGomkyK/file.html)

What I did was create a mock-up wav header with the info you provided, then forced FFmpeg to decode it as adpcm_yamaha using this command:

```
ffmpeg -acodec adpcm_yamaha -i input_path.wav output_path.wav
```
## Post #3
- Username: IlDucci
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 20, 2014 10:01 pm
- Post datetime: 2015-05-26T21:37:28+00:00
- Post Title: Alone in the Dark: The New Nightmare ADPCM format

YAMAHA AICA? Awesome, that means there's tools to create new audios. I'll check it out, thanks!
