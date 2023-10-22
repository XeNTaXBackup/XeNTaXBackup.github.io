## Post #1
- Username: Mattrio
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jan 31, 2016 9:57 pm
- Post datetime: 2016-02-04T19:14:19+00:00
- Post Title: [RESOLVED] Visceral .str compression files for audio

Hello,
I am trying to get audio files from Visceral's MySims Racing and MySims SkyHeroes. Both are using .str compressed files with true .aiff audio files in, and I can't manage to extract them. In the researches I did I've found that Visceral Games are using this kind of compressed files for other of their games too, such as Dead Space, however Gibbed.Visceral.StrPack does not manage to extract these str files. Any ideas? Thanks.

One of these str files: [http://www.mediafire.com/download/d44n8 ... inmenu.str](http://www.mediafire.com/download/d44n8xwodyhot8r/mainmenu.str)
It contains 44 aiff audio files.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-02-10T12:10:55+00:00
- Post Title: [RESOLVED] Visceral .str compression files for audio

Definitely FSB4 headers. But they aren't uncompressed AIFF audio. Those are just the original filenames before they are compressed using FMOD technology.

Use FSBii from HCS to separate the files

Then you can use vgmstream to playback / convert the audio.

To convert the FSBs, use vgmstream's "test.exe"

Use this batch script to convert these quickly.

```
FOR %%a IN (*.fsb) DO test -l 1 -f 0 -o "%%a.wav" "%%a"
```
## Post #3
- Username: Mattrio
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jan 31, 2016 9:57 pm
- Post datetime: 2016-02-20T13:18:16+00:00
- Post Title: [RESOLVED] Visceral .str compression files for audio

It works! Thanks a lot.
