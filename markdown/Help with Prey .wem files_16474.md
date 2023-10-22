## Post #1
- Username: jflieger
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 11, 2017 10:59 am
- Post datetime: 2017-06-29T21:13:31+00:00
- Post Title: Help with Prey .wem files?

I'm trying to use revorb and ww2ogg to convert the voice files inside of the Localization folder into a usable format, but no matter what I try, nothing seems to work. I always get an error inside of the command window for all of the files I try to convert that reads "Parse error: expected 0x42 fmt if vorb missing." I can't seem to find any solutions online.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2017-06-29T22:12:09+00:00
- Post Title: Help with Prey .wem files?

The error you are getting is stating that the .wem files aren't encoded in vorbis.

It will be either PCM or ADPCM since it is not vorbis as long as the .wem files are from the PC version.


PCM you can just try and raw importing the file into audacity as PCM RAW and if it doesn't play static, then you're all good.

ADPCM you can try the tool I have attached to this post to decode it into .wav

If that doesn't work, upload a sample.
[Wwise ADPCM Converter 0.9.9.7z](https://xentaxbackup.github.io/file/13056_Wwise ADPCM Converter 0.9.9.7z)
## Post #3
- Username: jflieger
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 11, 2017 10:59 am
- Post datetime: 2017-06-30T03:35:20+00:00
- Post Title: Help with Prey .wem files?

> Reply from brendan19
>
> The error you are getting is stating that the .wem files aren't encoded in vorbis.

It will be either PCM or ADPCM since it is not vorbis as long as the .wem files are from the PC version.


PCM you can just try and raw importing the file into audacity as PCM RAW and if it doesn't play static, then you're all good.

ADPCM you can try the tool I have attached to this post to decode it into .wav

If that doesn't work, upload a sample.

Alright, tried the PCM raw import and got static like you said. Downloaded the tool you attached, and I tried running it in the same directory as one of the .wem files and just got a short command window popup and close, also tried clicking and dragging the file onto the .exe and got the same. I might be doing something wrong though. Here's a sample if that helps:
[934974095.rar](https://xentaxbackup.github.io/file/13057_934974095.rar)
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2017-06-30T07:25:56+00:00
- Post Title: Help with Prey .wem files?

1. Open up the folder containing the Wwise Sound Tool
2. Hold down shift and right-click inside the folder and choose "Open command window here"

Type the following

```
"Wwise Sound Tool.exe" decode_all *.wem
```

Then press enter two times.

Done
