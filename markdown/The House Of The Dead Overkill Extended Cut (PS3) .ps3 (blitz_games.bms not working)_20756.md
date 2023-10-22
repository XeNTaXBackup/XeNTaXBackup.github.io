## Post #1
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2019-07-01T15:19:55+00:00
- Post Title: The House Of The Dead: Overkill: Extended Cut (PS3) *.ps3 (blitz_games.bms not working)

Hi guys, I've just run into some trouble trying to unpack archives with streamed sounds from a game that might be unofficially called "House Of The Dead 5": whenever I use the BMS I mentioned QuickBMS.exe extracts some files then stops with an incomplete file error & total size of unpacked content is way smaller than size of a given archive (with *.ps3 extension).
So far I attempted to extract 4 such files but there're many more.

You can find [example files here](https://mega.nz/#!lF8QhazJ!F-YhASOpJOPddiX5PqQhDwldAQIil2eYwUh9U8a2QVE), good luck with them and thanks in advance!
Regards, GenericRipper.

PS. I almost forgot to mention that I use [this](http://aluigi.altervista.org/bms/blitz_games.bms).
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-07-01T22:19:11+00:00
- Post Title: The House Of The Dead: Overkill: Extended Cut (PS3) *.ps3 (blitz_games.bms not working)

It's a bit of a weird format, but the audio all seems to be standard PSX, 44100 Hz, stereo, interleave 0x8000.

The files with "_start" and its corresponding "_end" file need to be joined together before they can be played properly - this will give a single headerless music file.

The other files ("l2" and "l3") contains lots of individual sounds/scenes.  Even though it's standard PSX audio, PSX doesn't seem to recognise it.  The format seems modified from what that BMS script can recognise.

I'll have a go at modifying it.  It shouldn't be too difficult to get it to work (if someone hasn't already done so).
## Post #3
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-07-01T23:07:56+00:00
- Post Title: The House Of The Dead: Overkill: Extended Cut (PS3) *.ps3 (blitz_games.bms not working)

Ok, here's my script to extract those .ps3 archives (not the "start"/"end" ones).  Once extracted, the .wav files are sound info - these contain information on sample rate, channels, etc.  The .str files are the actual headerless audio data in PSX format.

Are there more files to go with the "start"/"end" ones as they seem incomplete?  For example, is there a part 2, part 3 ... etc?


# House Of The Dead: Overkill (Extended Cut) (PS3)
# BMS script By Dave, 2019

Endian big

Get JUNK Long
Get ALIGN Long
Get JUNK Long
Get FILES Long
Get FILE_INFO Long
Math FILE_INFO * ALIGN
Goto 0x28
Get NAMES_TABLE Long
Math NAMES_TABLE * ALIGN

FOR A = 1 to FILES

	Goto FILE_INFO
	Get FILE_START Long
	Math FILE_START * ALIGN
	Get JUNK Long
	Get FILE_SIZE Long
	Get NAME_OFFSET Long
	Get JUNK Long
	Math NAME_OFFSET + NAMES_TABLE
	Goto NAME_OFFSET
	Get FILENAME String
	Log FILENAME FILE_START FILE_SIZE
	Math FILE_INFO + 0x14

NEXT A
## Post #4
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2019-07-02T19:03:04+00:00
- Post Title: The House Of The Dead: Overkill: Extended Cut (PS3) *.ps3 (blitz_games.bms not working)

Thanks a lot DKDave, your script works perfectly on all *.ps3 files!
BTW the files with "_start" and its corresponding "_end" file are only my custom cuts, I made those because some *.ps3 files were too big to upload them (for example soundstreaming_l6.ps3 is 110 МB while soundstreaming_l1.ps3 is 125 МB).

All the best!
