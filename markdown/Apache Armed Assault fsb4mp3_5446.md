## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-11-23T11:06:09+00:00
- Post Title: Apache Armed Assault fsb4/mp3

This game uses FSB4 "container" and the audio are compressed with mp3, extract the audios is not a problem, but reconvert them to wav  looks more difficult.

I can convert to wav some files but not all of them, i get .wav with sizes of 44bytes, 600bytes, etc 

Mplayer/ffmpeg and dbpoweramp don't recognize the files

I attach a exctrated files (mp3) using the latest fsbext (from Aluigi), to see if someone knows a way to convert the mp3 to wav.

Here it's the ful file (38mb's)
[http://www.mirrorcreator.com/files/1S1P ... .fsb_links](http://www.mirrorcreator.com/files/1S1PQVTC/english_v_afr.fsb_links)
[altitude_1200_p2.mp3](https://xentaxbackup.github.io/file/3636_altitude_1200_p2.mp3)
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-11-24T02:58:03+00:00
- Post Title: Apache Armed Assault fsb4/mp3

The individual streams need to be padded out to 32 bytes in order to find them, no idea why the sizes aren't padded as well.  I've added support to fsb_mpeg 0.11 for this, unpack like:
fsb_mpeg.exe english_v_afr.fsb -p 16 -b 32

[edit] quick fix, there's a lot of files with the same internal name here, 0.12 gives each subfile a unique prefix to avoid overwriting stuff
## Post #3
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-11-24T07:58:41+00:00
- Post Title: Apache Armed Assault fsb4/mp3

Works great!!
If someone don't know where to download the tool here is:
[http://hcs64.com/files/fsb_mpeg012.zip](http://hcs64.com/files/fsb_mpeg012.zip)
