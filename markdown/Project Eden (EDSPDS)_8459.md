## Post #1
- Username: Herf
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Mar 02, 2012 2:47 pm
- Post datetime: 2012-03-03T07:08:58+00:00
- Post Title: Project Eden (EDS|PDS)

Hello to everyone.
If anyone remember this game, it had some nice ambiance.
However, ripping is the problem. Can anyone help?
Here are some sound files from PC and PS2 version:
PS2: [http://dl.dropbox.com/u/48495960/CS09.ZIP](http://dl.dropbox.com/u/48495960/CS09.ZIP)
PC: [http://dl.dropbox.com/u/48495960/Cutscene09.zip](http://dl.dropbox.com/u/48495960/Cutscene09.zip) (Same file, but from PC version).
Thanks in advance.

(Managed to find out that PC version contains some kind of ADPCM format, but everything failed to play it).
## Post #2
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2012-03-03T17:22:55+00:00
- Post Title: Project Eden (EDS|PDS)

The PS2 version contains standard Sony ADPCM.  It seems to contain some movie dialogue for multiple languages.  I don't have time to figure out the virtual file system right now, but that should get you started.

If you want a quick listen, trim the first 0x2000 bytes and change the file extension on what's left to .MIB.  It will work with the [vgmstream WinAmp plugin](http://hcs64.com/files/vgmstream/).  Be sure to read the readme file as some external .dll files are required for use.

Good luck.
## Post #3
- Username: Herf
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Mar 02, 2012 2:47 pm
- Post datetime: 2012-03-03T19:38:20+00:00
- Post Title: Project Eden (EDS|PDS)

Thanks for replying.
It actually worked, but sounds still sounds like garbage.
In the meantime, I'll try to figure out the frequency. Some tests showed that it's somewhere in the between 22050 and 44100.
Thanks again.
