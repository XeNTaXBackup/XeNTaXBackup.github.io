## Post #1
- Username: MrSinistar
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Sep 30, 2012 5:20 am
- Post datetime: 2012-09-30T20:45:02+00:00
- Post Title: MegaRace Music Modules for Adlib (*.sdb)

Hi guys,

I've been messing around with MegaRace's files for a long time and I would love to get some help on viewing them outside of the game. 

The first thing I did was extract the files from inside the MEGARACE.DAT file on the CD using Game Extractor.  Then I found a file called NEWSAN.hsq; HSQ is Cryo's compression format based off of LZ77 and the name of the file is one of the race tracks in the game.  I used a program that's been floating around on the internet called unHSQ to decompress the file and it spits out NEWSAN.___ (though it should be NEWSAN.sdb...I don't know why unHSQ doesn't add on file extensions).  This final file is the uncompressed music module.  I compared it to other existing SDB modules from other Cryo games, like Dune and KGB and they seem to share the same headers and similar hex data.  There was only one player for the SDB file format and that's RDOSPlay, however when I load a MegaRace module into the player it crashes.

[http://dunerevival.svn.sourceforge.net/ ... tools/hsq/](http://dunerevival.svn.sourceforge.net/viewvc/dunerevival/tools/hsq/)  Here's the HSQ decompressors and source code, if you wanna mess around with the HSQ files.  

Bigs_fr has his decompressor already compiled, which is the program I used: [https://sites.google.com/site/duneedito ... edirects=0](https://sites.google.com/site/duneeditor/bigs_fr-mirror/unhsq.zip?attredirects=0)

Also, here's RDOSPlay, if you guys wanna look at that: [http://dunerevival.svn.sourceforge.net/ ... pathrev=97](http://dunerevival.svn.sourceforge.net/viewvc/dunerevival/tools/rdosplay/?pathrev=97)

Thanks in advance!!
## Post #2
- Username: MrSinistar
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Sep 30, 2012 5:20 am
- Post datetime: 2016-06-19T06:27:34+00:00
- Post Title: MegaRace Music Modules for Adlib (*.sdb)

Well, it only took 4 years but I was able to reverse engineer the majority of this music format.  I even wrote a new song and injected it into MegaRace, which is something I don't think anyone has done before.

The music data is basically MIDI but there's a couple of differences.  For example, the NoteOff events are missing their velocity byte so in order to make the music MIDI-compatible again, that byte must be added back in.  Also, the pitch bends only have one byte instead of MIDI's standard two bytes and actually have an 8-bit value range compared to the regular 7-bit value ranges that MIDI works with.  The working range is only 00-80 so it's only byte higher than MIDI's 7F limit.  The pitch bend range is 2 semitones up and 2 semitones down.  Other than that, the music notation is standard MIDI data.

The OPL2 instrument data is laid out very similarly to other OPL instrument formats but has an additional section of data that's devoted to additional parameters of the OPL chip that other sequencers and trackers normally didn't give composers access to.  This is what made the music from MegaRace stand out from other AdLib soundtracks at the time.  There's a series of bytes that control various things such as automated pitch bends, along with separate modulator and carrier volume curves, so you create some very nice sounding instruments.

Here's the music mod I did for MegaRace.  Since it's a French video game, I decided to add a French song to the game, so I picked Daft Punk's Aerodynamic as a test song.   

[https://www.youtube.com/watch?v=TqBJedId4g4](https://www.youtube.com/watch?v=TqBJedId4g4)

Even though I was able to reverse engineer the majority of the format, I can't code so I've been manually hex editing MIDI data to convert music from the game to MIDI and vice versa.  If anyone can help out with a simple program that can remove the velocity bytes for NoteOff MIDI events, that would be a great starting point.  I'm sure it wouldn't be too difficult.

Thanks for taking a look.
