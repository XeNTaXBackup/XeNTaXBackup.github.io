## Post #1
- Username: superblah12
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 29, 2010 11:56 am
- Post datetime: 2010-05-01T01:58:49+00:00
- Post Title: P.B. Winterbottom "music.xwb"

The music from "The Misadventures of P.B. Winterbottom" is some of the greatest music I've ever heard. I have the game for Xbox 360, but i recently discovered that if you owned the pc version you could extract the music out of  the aforementioned file "music.xwb" If i could get that it'd be awesome!
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-05-01T07:54:55+00:00
- Post Title: P.B. Winterbottom "music.xwb"

Well, we need a file to work with.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-01T10:34:35+00:00
- Post Title: P.B. Winterbottom "music.xwb"

the reference topic with the whole 84mb file is:
[viewtopic.php?f=17&t=4363&start=0&st=0&sk=t&sd=a](http://forum.xentax.com/viewtopic.php?f=17&t=4363&start=0&st=0&sk=t&sd=a)

quick step-by-step:

get unxwb:
http://aluigi.org/papers.htm#unxwb
then from the command-line or bat file:
unxwb.exe -d c:\output_folder c:\music.xwb
OR (as suggested by other people to get some filenames)
unxwb.exe -b c:\music.xsb 0x4da -d c:\output_folder c:\music.xwb
use a player that support the ms adpcm codec like vlc or mplayer/mencoder to play them
