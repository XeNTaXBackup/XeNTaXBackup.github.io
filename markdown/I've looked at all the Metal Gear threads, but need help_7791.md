## Post #1
- Username: DXSnakeEater
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 02, 2011 6:57 am
- Post datetime: 2011-12-01T23:48:12+00:00
- Post Title: I've looked at all the Metal Gear threads, but need help

Hi, I know this is a sucky introduction. I understand. I extracted every file off both of my MGS3 Subsistence discs, and I can't seem to figure out how to convert the MTAF files and such from BGM.DAT into a format that works. Could anyone tell me how to do this? I was able to go through the VOX.DAT files and got them to work fine in MFAudio, but that was about it.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-12-02T06:29:47+00:00
- Post Title: I've looked at all the Metal Gear threads, but need help

Newer versions of [vgmstream](http://hcs64.com/vgmstream.html) can decode the extracted MTAF files.  You should get the latest zip from [>here<](http://hcs64.com/files/vgmstream/) , choose either the winamp plugin in_vgmstream.dll or the command line decoder test.exe, and get the external dlls from [>here<](http://hcs64.com/files/vgmstream_external_dlls.zip).  With test.exe you can convert the files to standard .wav like so:
```
test.exe -o output.wav input.mtaf
```
## Post #3
- Username: DXSnakeEater
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 02, 2011 6:57 am
- Post datetime: 2011-12-03T05:18:26+00:00
- Post Title: I've looked at all the Metal Gear threads, but need help

Holy crap! It worked! Thanks man!
