## Post #1
- Username: Dei3i
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 18, 2017 12:35 am
- Post datetime: 2017-02-17T17:25:22+00:00
- Post Title: Torment - Tides of Numenera .bnk files

Hello forum!

This is my very first post so... (if there's something wrong with it: i apologize.. - and yes i did read the rules)
The game in question is Torment: Tides of Numenera by InXile entertainment.

I spent today looking for information about possible methods on "converting" (i don't know if that is the proper word for this)
the game files to obtain listenable .wav (or other easily playable file type) files from the games files.
The game hasn't even been properly released yet but i'm one of the backers to the game and i have access to the early-access version
of the game on Steam. Since the game was released (to be tested) i've been trying to find some way to listen to it's soundtrack outside the game.
The game has gone through multiple changes during this time and now it's almost ready for release. The release is slated for 28th of February 2017.
The music for this game is composed by the great Mark Morgan who is responsible for some of the best game soundtracks around (the original Planescape game for example)
The music in this game is the reason why i'm trying to extract the files. I'm quite sure there are loads of fx sounds and snippets of dialogue to be found in the files as well.
While i fully accept that the people responsible for the game want compensation for their efforts (i have backed the game and will get the soundtrack when the game arrives)
the reality is often such that the released soundtrack CD doesn't include all the music and ambient sounds i would like to listen to. 
My purpose is not to share this music/ambient sounds but to obtain some sort of means to listen to them outside the game.
I have enormous respect for everyone involved and i don't want to hinder anyones livelihood. 

To the point: i have found .bnk files from searching the game files and even a readable text of information about the music and information about the placement of the music in the file.
Using the bnkextr.exe i was able to extract 46 different bankdata files from one of the archives called "MUSIC" (bnkextr output was .wav files)
I then proceeded to try my luck with converting the files to .ogg with no luck. I used the tools ww2ogg and revorb in tandem with the batch scripts but got only errors (Parse error: unknown chunk type) 
after trying that i extracted the .bnk file again to get to the beginning. I started reading about different codecs and headers which could be causing the problem.
I tried to listen to the output .wav files as ADPCM with no luck. Tried to use wwise sound tool but didn't get the program to start.
Tried using ima_rejigger with the bat file to remove or alter the headers (that's what i gathered it does) to render the files to a playable format with no luck.
This is pretty much where i am at right now.

On a curious sidenote the output .wav files from the original .bnk archive all have listed durations if i load them to foobar 2000 but the aforementioned player reports an
error while trying to decode the file: "Unable to open item for playback (Missing ACM codec)" When i tried to look for ACM codecs i was always directed to ADPCM which got me thinking that the file was in that format. Perhaps my intuition serves me wrong.

Anyone have any insight they want to share with this?
## Post #2
- Username: Dei3i
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 18, 2017 12:35 am
- Post datetime: 2017-02-21T17:03:54+00:00
- Post Title: Torment - Tides of Numenera .bnk files

trying to read/play the files (extracted bankdata.xxx files from "audio.bnk") with classic media player (MPC-HC) 
results in error message(s) like this: 

File Source (Async.)::Output
Wave Parser::output
Audio Switcher::Out

Media Type 0:
--------------------------
Audio: 0xfffe 48000Hz stereo 132kbps

AM_MEDIA_TYPE: 
majortype: MEDIATYPE_Audio {73647561-0000-0010-8000-00AA00389B71}
subtype: Unknown GUID Name {00753000-00E0-0000-597E-28000000C003}
formattype: FORMAT_WaveFormatEx {05589F81-C356-11CE-BF01-00AA0055595A}
bFixedSizeSamples: 1
bTemporalCompression: 0
lSampleSize: 4
cbFormat: 66

WAVEFORMATEX:
wFormatTag: 0xfffe
nChannels: 2
nSamplesPerSec: 48000
nAvgBytesPerSec: 16586
nBlockAlign: 4
wBitsPerSample: 16
cbSize: 48 (extra bytes)

pbFormat:
0000: fe ff 02 00 80 bb 00 00 ca 40 00 00 04 00 10 00 þÿ..€»..Ê@......
0010: 30 00|00 00 02 31 00 00 00 30 75 00 e0 00 00 00 0....1...0u.à...
0020: 59 7e 28 00 00 00 c0 03 c0 1c 00 00 a0 1d 00 00 Y~(...À.À... ...
0030: cb 01 c0 03 d4 40 00 00 b4 42 00 00 0e a3 c0 b6 Ë.À.Ô@..´B...£À¶
0040: 08 0b                                           ..

Makes me think this is a file with a wwise header that the player can't handle.

Anyone have any ideas on how to try to proceed?
