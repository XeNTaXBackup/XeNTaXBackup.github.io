## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-02-04T21:23:35+00:00
- Post Title: Shakii the Wolf (PC/Dos) *.KPF files

Not sure what to make of these other than that they seem like the music used by the game in some odd MIDI-like format, since some reference instruments. I have most of the game files figured out except these.
[KPFs.rar](https://xentaxbackup.github.io/file/2767_KPFs.rar)
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-02-07T23:02:59+00:00
- Post Title: Shakii the Wolf (PC/Dos) *.KPF files

Yes, looks like some kind of MIDIish format. The problem with MIDI in general is that it just sends commands to the soundcard to play certain banks. So reerse engineering these can be really difficult. In your case, the KPF files are either a song or an instrument bank so it wouldn't even be possible to convert them to standard MIDI. I wouldn't promise myself that anyone has this much knowledge about MIDI formats these days.
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-02-08T18:44:17+00:00
- Post Title: Shakii the Wolf (PC/Dos) *.KPF files

Thanks for the reply. And I see, it isn't exactly conversion, but more-so, kinda wondering, for all I know, these could not be that far from XMID or MIDI, as I hear them ingame. I could possibly get a recording of how one of them sound ingame and try replacing files and see if it has an effect.
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-05-23T22:00:28+00:00
- Post Title: Shakii the Wolf (PC/Dos) *.KPF files

Just updating on what I've done so far, Shakii uses an Adlib sound bank that can be read and converted (DLS, ITI instruments, etc). This makes me believe that the songs may be a form of ROL.

I'll use Dosbox Debug more to see what else comes up.

Update: The Music can be converted to DRO using DosBox, which can then be further converted with tools.
