## Post #1
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-03-31T08:34:08+00:00
- Post Title: wwise .bnk and .wem files

The recently released "early access" version of Rollercoaster Tycoon World uses wwise for audio (it has an AkSoundEngine.dll file). The audio appears to be stored in both .wem files and .bnk files. 
Does anyone know how to extract the audio from the .wem and .bnk files into something I can listen to? And also whether its possible to convert audio back into .wem and .bnk files without the need to buy the full wwise SDK?
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-03-31T10:28:24+00:00
- Post Title: wwise .bnk and .wem files

It's possible that the .wem files can be decoded with [ww2ogg](https://github.com/hcs64/ww2ogg), seems likely that they're Wwise Vorbis on the PC.
## Post #3
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-04-03T21:48:31+00:00
- Post Title: wwise .bnk and .wem files

Managed to convert the .wem files out (they seem to be the music tracks which is the bit I care about, the .bnk files must contain the sound effects) but now I need to find a way to produce new .wem files to replace them. Any ideas?
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-04T16:09:14+00:00
- Post Title: wwise .bnk and .wem files

Full wwise SDK will not help you putting them back. But if they are just separate WEM files, you can use free wwise version to do it.
## Post #5
- Username: chrysls
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 05, 2016 8:27 pm
- Post datetime: 2016-07-05T12:40:44+00:00
- Post Title: wwise .bnk and .wem files

You CAN change audio in BNK files saving header's info and other things, use soundbank-editor.
