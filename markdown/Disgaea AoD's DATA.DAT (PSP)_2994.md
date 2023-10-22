## Post #1
- Username: flonne
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Apr 02, 2008 8:01 pm
- Post datetime: 2008-04-04T03:18:25+00:00
- Post Title: Disgaea: AoD's DATA.DAT (PSP)

hello everyone! I've been trying to uncover the format of DATA.DAT from the game Disgaea: Afternoon of Darkness for PSP, which is a port from the PS2 game, Disgaea: Hour of Darkness. Though I've found traces of some files within, I'm still rather confused as to where the entry table is. Please help me out if time permits =)

First of all, i must say that i DID search and i know that Mr. Mouse has written a script to extract files for the PS2 version ([viewtopic.php?f=15&t=2137](http://forum.xentax.com/viewtopic.php?f=15&t=2137)). I have found the format to be different as there is no sector.h outside the file(perhaps compressed in DATA.DAT itself). 

Before I share what I know about the file, here's where you can get DATA.DAT if you wish to help out. 
[http://www.mininova.org/tor/1040408](http://www.mininova.org/tor/1040408) - Torrent DL of Disgaea game
[http://umdgen.ps3news.com/UMDGen_v4.00.rar](http://umdgen.ps3news.com/UMDGen_v4.00.rar) - UMDGen to extract DATA.DAT from the cso image.
simply drag the cso image file into UMDGen and DATA.DAT can be found in /USRDIR

I'll start with a list of files you'd expect(reference from PS2 version)
inside DATA.DAT there's a start.dat which contains more files.
complete filelist can be found @ [http://pastebin.com/f7e0766fd](http://pastebin.com/f7e0766fd)


This are my guesses for the PSP's DATA.DAT. I'd expect the same files within this archive except audio files, which have been converted to AT3 format. in DATA.DAT i have found hints of these files. please note that the file names are just guesses by me with reference from the PS2 version.

```
10000             DUMMY(just a few bytes which spells dummy)
18000             DATA.DAT(smaller version similar to PS2 version)
76F0000         SNDPAK.PAK(found the first RIFF file here, followed by many many more)
363C0000       start.dat(originally within DATA.DAT of PS2 version), filenames script.dat, effect.km3, talk.dat, magic.dat, face.dat in plain text.

```


the RIFF files are actually AT3 format

```
                WAVEfmt
                           fact...
                           smpl...
                           data followed by [LONG data_size] followed by data[data_size]

simply save selection from RIFF to end of data block
download attached ATRAC3.zip, install to play music
```

details of file format here: [http://replaygain.hydrogenaudio.org/fil ... t_wav.html](http://replaygain.hydrogenaudio.org/file_format_wav.html)


that was my little progress so far.. i hope that anyone with some time in your hands could help out. my confusion comes from the partly compressed and partly uncompressed nature of the file, where some filenames can be seen while the rest cant, no tricks with the audio files either. i could be wrong, please enlighten me. I appreciate any help/hints given. Thanks in advance!
[ATRAC3.zip](https://xentaxbackup.github.io/file/1485_ATRAC3.zip)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-06-12T21:11:37+00:00
- Post Title: Disgaea: AoD's DATA.DAT (PSP)

People have looked at it, judging from the dowloads, but to no avail...
## Post #3
- Username: flonne
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Apr 02, 2008 8:01 pm
- Post datetime: 2008-06-16T11:56:50+00:00
- Post Title: Disgaea: AoD's DATA.DAT (PSP)

> Reply from Mr.Mouse
>
> People have looked at it, judging from the dowloads, but to no avail...
 perhaps it was too troublesome getting 10 files to unrar. posted torrent link and the extractor i used to extract data.dat

i've managed to swap some soundtracks within the game around. when re-archived umdgen it's able to play properly in-game too.

hopefully someone's interested. =)
