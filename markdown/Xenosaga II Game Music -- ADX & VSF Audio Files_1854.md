## Post #1
- Username: Xab
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 21, 2006 4:17 am
- Post datetime: 2006-04-20T20:59:29+00:00
- Post Title: Xenosaga II Game Music -- ADX & VSF Audio Files

When Monolith decided to only release the music for the in-game cutscene's and neglected the field and battle musics I began an unhealthy obsession to rip the game music directly from the discs. This post is a culmination of what I have found along the way, and a bit of help for those who are also seeking these missing tracks.

After scouring the net I stumbled upon a Xenosaga 2 file extractor. You may find it on these forums [http://www.alucard.cc/](http://www.alucard.cc/). The front page seems to be a tad broken, so you will have to work with the site to get to thier download area, but what you are looking for is Console Rip Creator under the PS2 general category. You will also need the XenoSaga II extractor plugin for CRC that is attached to a topic inside thier forum (requires an account to see the ps2 ripping forum).

Anyway, the files you want to extract can be found on either of the game discs. XENOSAGA.00 is the table and once concatenated, XENOSAGA.01 + XENOSAGA.02 is the data munge. Running these through CRC will produce a lot of *.ADX and *.PRJ/*.VSF files under the sound directory.

The battle music will be extracted as follows:
\@EXTRACTED\sound\adx\battle01.adx <--> Standard Fight
\@EXTRACTED\sound\adx\battle02.adx <--> Gear Fight
\@EXTRACTED\sound\adx\boss01.adx <--> Standard Boss
\@EXTRACTED\sound\adx\boss02.adx <--> Gear Boss
\@EXTRACTED\sound\adx\bosslast.adx <--> Final Boss

To play these ADX files you will need CinePack or ADX2WAV. Please note these files were meant to loop so some additional editing may be in order after converting them to WAV if you wish to loop a couple times and then fade out at the end.

Now, for the other music. If you look in \@EXTRACTED\sound\smf\ directory you will see many groups of files each named after a specific area in the game. For instance the following group is for 2nd Militia:

\@EXTRACTED\sound\smf\106_milchia2nd.mid
\@EXTRACTED\sound\smf\106_milchia2nd.prj
\@EXTRACTED\sound\smf\106_milchia2nd.vsf

These three files compose the complete song. The .MID file is in fact a standard MIDI file. You can even load it up in Winamp or Media Player, but it will sound either distorted or simplified as compared to when it is played from within the game. In fact, this a SAMPLED MIDI. Loading this MIDI file within CakeWalk (or your favorite MIDI sequencer) will reveal several channels with missing banks and patches.

The .PRJ seems to be some kind of header + table file while the .VSF is the sound bank which contains the samples. Ironically the VSF contains its own built-in table so the PRJ seems to be useless at this point. The .PRJ/.VSF pair are used in other parts of the game for regular sound effects like battles effects, character grunts, etc when the regular ADX format was too much. You can find these non-music related sounds in \@EXTRACTED\sound\vsf\ directory.


-------------------------
VSF File Format
-------------------------
[Header]
char[4] ID //Text or chunk ID. Usually "VSFp"
dword HeaderSize //Number of bytes in this header afterwards
dword RecordCount //Number of samples inside this file
dword TotalDataBytes //Total byte count for all record data (+= FileSize)
byte[HeaderSize - 8] HeaderPadding //null whitespace

[Record]
byte[8] RecPadding //Null whitespace. Presumably to align the record on data boundary.
word UNK1 //Suspected to be the Sampling Rate
word UNK2 //Block Size? Interleave? 
dword UNK3
word UNK4 //Suspected to relate to looping
word UNK5 //Suspected to relate to looping
dword FileSize //Size of the data
char[16] FileName //Always 16 characters, null padded. Internal file names that exceed 16 bytes are truncated. Some files will be missing extentions.
byte[FileSize] FileData //Binary "Sony ADPCM" data.

.. Repeats RecordCount times.

As seen above I have taken guesses to the actual data for the record. I am fairly certain that UNK1 is the sample rate but I have also seen some non-standard numbers showing up here as well.

You can use MFAudio or Cube Media Player to play these samples if you give the correct offsets, but even after tinkering around I was unable to conclusivly identify the correct interleave or block align to make the sound come out correctly across the many different files.

---------------------------
Some Sample Data
---------------------------
203_game_over.vsf:

[Record #2]
0x80: 00 00 00 00 00 00 00 00
0x88: 48 71 (Dec: 29000) //Sample Rate?
0x8A: 3C 00 (Dec: 60) //Block Size? Interleave?
0x8C: AA 09 00 00 (Dec: 2474)
0x90: B0 BF (Dec: 49072) //Start of loop?
0x92: 17 00 (Dec: 23)
0x94: 40 00 03 00 (Dec: 196672) //file size
0x98: 53 6F 75 6E 64 20 35 2E 77 61 76 00 00 00 00 00 // "Sound 5.wav" -- file name
0xA8: ... Data

My goal is to ultimatly extract these banks to WAV files and then import them as sound fonts to be used with the MIDI file... but currently I am struggling with finding ANY information on the Sony ADPCM format... So ANY pointers to a VAG/XA format or source code to a working decoder would be greatly appreciated!

Note: Due to forum restrictions on uploaded file size I have uploaded the music track for the menu as opposed to the given example above as it was the smallest.
[201_menu.zip](https://xentaxbackup.github.io/file/712_201_menu.zip)
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-20T21:16:23+00:00
- Post Title: Xenosaga II Game Music -- ADX & VSF Audio Files

It looks like a variation on the Sony VAG format.
you could try decoding some of the samples using

[http://www.fmjsoft.com/aamain.shtml](http://www.fmjsoft.com/aamain.shtml)

it is shareware, but i hope it can decode vag without registering.

currently havent found any relevant information though on how too
decode the Sonys ADPCM, but maybe you could mail the author of
that program and ask him for details? =o

if you find something, im interested aswell. ive been looking into VAG before
but i stopped due too lack of info.

i have seen lots of different VAG files out there in games, but all with different headers. but the data is structured just the same way.

EDIT: Oh yes. definitely VAG file with new header. ive seen this structure of an audio file in atleast 90% of all PSP games i have ripped.
## Post #3
- Username: Xab
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 21, 2006 4:17 am
- Post datetime: 2006-04-21T21:31:35+00:00
- Post Title: Xenosaga II Game Music -- ADX & VSF Audio Files

You are correct. The sound data is indeed a VAG compressed stream. I downloaded the program you referred to and comverted a wav file I had laying around to look at the file format. The format is as follows:

*BIG Endian*

[VAG Format]
char[4] ID //"VAGp"
dword HeaderSize //usually 32
dword UNK1 //Unknown. was 0 for my convert. may be a format type
dword DataSize //Number of bytes of the waveform data
dword Frequency //Sample Rate of the waveform data
byte[HeaderSize - 20] Padding //Header Align padding
char[16] FileName //Name of the file
byte[DataSize] FileData //The waveform data

I wrote a VAG header to one of the raw chunks I was getting in the VSF and then loaded it up in MFAudio and lo and behold it plays back perfectly. Now to decipher how to decode the waveform and produce audio, but this is a big start as I can use MFAudio to convert them to WAV.

Also, I managed to get a hold of the official Sony VAG converter and the official Sony VAB bank tool.

After playing around with the VAB Tool for a bit it looks like the *.PRJ files very closely resemble the data that is written to VAB. But once again the layout was bastardized by Monolith. So it looks like that in fact, PRJ is the "VH" (VAB Header) file and the VSF is the "VB" (VAB Body). The main differences is the "Program" which is written to a seperate "S" file by the official tool is included directly in another RIFF section of the PRJ and it looks like the byte order (little endian) and placement is different. 

Since VAB contains many controls for changing pitch, volume, and all kinds of audio goodness, this will probably be important to decipher in order to reproduce the MIDI files perfectly.

In the mean time, I am attaching a small .NET program I wrote to read and extract VSF files to either Raw or as a VAG file (with the correct header). C# source code included.

Again, if anyone has any information on how to decode the VAG waveform data please point me in the right direction-- would be most appreciative!
[vasfextractor.zip](https://xentaxbackup.github.io/file/717_vasfextractor.zip)
## Post #4
- Username: Vector Harbor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 14, 2019 7:27 am
- Post datetime: 2019-03-13T23:32:53+00:00
- Post Title: Xenosaga II Game Music -- ADX & VSF Audio Files

Hi, I was wondering if there is a other tool to extract the music from the file XENOSAGA.01 & XENOSAGA.02 ? 


And yes i'm aware that this thread is 13 year olds but this is the only thread that talks about.
## Post #5
- Username: Habanero
- Rank: n00b
- Number of posts: 19
- Joined date: Thu May 02, 2019 2:36 am
- Post datetime: 2020-08-17T06:03:41+00:00
- Post Title: Xenosaga II Game Music -- ADX & VSF Audio Files

Anyone ever make any progress trying to rip Xenosaga II audio? I'm just now trying.
