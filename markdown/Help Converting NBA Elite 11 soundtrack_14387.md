## Post #1
- Username: tornado1014
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 23, 2016 6:27 pm
- Post datetime: 2016-05-23T10:42:12+00:00
- Post Title: Help Converting NBA Elite 11 soundtrack

Hello!

I am currently trying to convert the soundtrack for this game into .wav or .mp3 or something playable. I have looked into both EALayer3 and ffmpeg codecs to decode the .sns file, without success.

Trying to decode it with EALayer3 tells me that "the bitstream format is not readable". ffmpeg gave me a similar error.

I've been stalking this site plus a few others until I decided to sign up and ask for help just because I can't seem to get around this, no matter what I try.

I believe it is probably because it is a very specific codec, as I find that EA has used several different ones for their games over the years. Hopefully the codec isn't proprietary to this one game? Please, if anyone can, try giving this file a shot. It would definitely be greatly appreciated.

Thank you very much!!

[https://drive.google.com/open?id=0B802M ... HpXWElaaVE](https://drive.google.com/open?id=0B802M42UiChbajA4RHpXWElaaVE)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-04T15:46:42+00:00
- Post Title: Help Converting NBA Elite 11 soundtrack

It is not in any way specific codec. Its the most used codec in all EA games: EA XAS ADPCM.

But it has no header. So assuming its stereo 44100 khz sound, I'm adding these bytes to the beginning of the stream:

04 04 AC 44 00 00 00 00

And it gets converted with my Xas_decode tool. Here's the latest version.
[xas_decode.rar](https://xentaxbackup.github.io/file/11011_xas_decode.rar)
