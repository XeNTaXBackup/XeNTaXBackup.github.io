## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-14T13:57:09+00:00
- Post Title: EA audio extraction

Here's how I see the current situation with EA audio extraction. Please correct me if I'm missing something.

1. In case of frostbite, the are working dumpers for all known games. We just need to summarize it in one place, and describe possible problems. The difference is basically in .ebx format and chunk compression. There may be some other special cases though. Options for extracting only audio ebx/chunks would be useful too. By the way, what is dbx?

2. Most games use either XAS ADPCM or EAlayer3. Rarely it can be PCM or speex.

3. EAlayer3 is probably working for most cases now, though some problems exist:
- uncompressed samples still not supported, meaning if you decode sound to mp3, and there are some uncompressed samples in the beginning, they are just skipped. To decode them, you have to decode the whole file to WAV.
- multichannel mp3's by default extracted as many stereo mp3 files. 4ch - 2 files, 6ch - 3 files. To get proper multichannel sound you have to decode only to WAV, and there's still channel order problem, because games use different order, and no way to detect it.
- in case of many sounds joined together in one file, zench's version tried to decode them all, which is not always right. It will fail in some cases. And if decoder script already knows where all segments are, it will produce unwanted extra output. For example instead of 4 files, in will give you 10 duplicated files. Thus I temporarily removed that "multi-part decoding" from ealayer3, but I think it's better to introduce a switch for this.

4. XAS. As far I know, there's no standalone tool for this, and the only means to handle it is to use TOWAV after making extra header. Maybe I need to write a new decoder/encoder for this format, that will allow to handle all variations of it, and may be used in scripts too.
## Post #2
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-04-14T18:49:10+00:00
- Post Title: EA audio extraction

Many possibilities about .dbx files:

_Old version of .ebx files (Bad Company 2, for example).
_Geometry files?
_Shader info file?

I think I'm not far from the truth with the first one.
