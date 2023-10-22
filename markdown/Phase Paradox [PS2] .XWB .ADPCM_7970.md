## Post #1
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-01-01T22:25:30+00:00
- Post Title: Phase Paradox [PS2] .XWB .ADPCM

Hi there! 

I'm on a quest to extract music from an obscure survival horror game Phase Paradox. 
Developed by SCEI and released in Japan only.
The goal is for all tracks to have their respective names and I actually got fairly close to it but something is just not working right.

Here are the steps so far:

Background music is stored in 4 separate XWB containers in SND_DATA folder.

EVBGM.XWB
BGM.XWB
ENDING.XWB
OPENING.XWB

Each XWB container has a corresponding XWH (1kb) file to it, and if opened in notepad it will show the real filenames of the contents of XWB file.

Strangely enough none of regular xwb unpackers seemed to work with these files. I tried unxwb, XWB Extractor 1.1, EkszBox-ABX v2.0 to no avail. 
Ok, next I used Cube Media Player, and it found the tracks identifiable as PS2 ADPCM Audio.
The interleave needs to be set to 16 to make them playable.
It scanned and found 23 adpcm files inside EVBGM.XWB (which is the largest one and keeps most of bgm in it), but there's definitely more than 23 file names in EVBGM.XWH! 
So I opened several extracted/converted wav files in Sony SoundForge and saw that these wav files had more than just one track in them, separated by a few seconds of silence, hence more file names in XWH file.

I though - well that's not a problem, I'll just manually cut each one out and name them accordingly to tracklist in EVBGM.XWH. But The problem is Cube Media Player does not find the tracks in the same order as the tracklist goes in XWH file. So the names don't match, I'm certain of that because there would be names like bgm_02_01 bgm_02_02 bgm_02_03 and these names are meant to be be for 3 tracks inside one wav file, three tracks that sound similar but have some slight variations to it. I confirm it because there are some wav files that have exactly what I'm talking about. Since it starts with bgm_02, you'd expect it to be the 2nd file on the list in CubeMediaPlayer right?, but it's not... it will be 6th or 7th file along the road, and so that's how they all get mixed up. 

Plus some wav files clearly have more than one track because the next track would sound totally different from the previous, but there's no silence in between them and the next tracks just starts abruptly.

So I was wondering if someone could help out with this case and write a quickbms script, to separate all tracks in the right order, and (if that's not too much to ask) to have the proper names as seen in XWH files.

Attaching all 4 XWB + XWH couples:

[http://www.mediafire.com/?gkw94ez74vm2x9s](http://www.mediafire.com/?gkw94ez74vm2x9s)
[http://www.mediafire.com/?vd8wwbvdzjv3vwb](http://www.mediafire.com/?vd8wwbvdzjv3vwb)
[http://www.mediafire.com/?mtysr2mlhclsfq1](http://www.mediafire.com/?mtysr2mlhclsfq1)
[http://www.mediafire.com/?inmno8hbzmdua5v](http://www.mediafire.com/?inmno8hbzmdua5v)
## Post #2
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2012-01-06T21:55:24+00:00
- Post Title: Phase Paradox [PS2] .XWB .ADPCM

Hey bro.

Yeh, I've seen this exact XWH+XWB format mashup in a few other ps2 games just from memory.
I remember writing some lines of script some time ago to extract individual streams from the these sound-banks, but this particular script was amongst the 2.5TB worth of various game stuff that was on a HDD of mine, which spontaneously decided to go on a permanent, one-way holiday (to hell).

Whatever, enough of my pathetic venting & such...
I've written a new one just for you that works on all of the banks which you prudently uploaded (see below.)

Just to clarify some things for you though (out of respect, not criticism):
You mentioned you used "unxwb, XWB Extractor 1.1, EkszBox-ABX v2.0"; these tools (as well as others very much the same as these) are meant specifically for XBOX wavebanks, hence the extension 'XWB'. So the odds of seeing one of those particular XWBs on a PS2 game are pretty-much none.
It's nothing to feel silly about though, as it's a highly common misconception that all files are seemingly labelled and/or addressed so as to be 'user-friendly', when in-fact (when it comes to videogame files) it's the complete opposite. The exception being intentionally-moddable games.
As I often say: don't rely on the extension of a file to shed any light on the anatomy within...

Cube Media Player is a bit messy, you might only wish to use it as a very last resort because the layout and alignment of PS2-ADPCM at times can be highly-ambiguous, often difficult to discern.

```
open FDDE XWB 1

idstring RXWS
get RXWSsz long	# minus 16byte header
get UNKNOWN long	# 0x200
get NULL long
idstring FORM
get FORMsz long	# -16
get UNKNOWN long	# 0x100
get NULL long
get STREAMS long

set FTXT_LOC long FORMsz
math FTXT_LOC += 0x20
goto FTXT_LOC
idstring FTXT
get FTXTsz long
get UNKNOWN long	# 0x100
get NULL long
savepos FTXT_LOC
log MEMORY_FILE FTXT_LOC FTXTsz
get STREAMS2 long MEMORY_FILE	# synonymous with 'STREAMS' value

goto 0x24

for i = 0 < STREAMS
	get UNK1 short	# 0x1c00
	get UNK2 short	# 2/3
	get UNK3 long	# 0x7f7f
	get UNK4 short	# 0x200
	get FREQUENCY short
	get NULL long
	get OFFSET long
	get SIZE long
	get LOOP_POS long
	
	get STPOS long MEMORY_FILE
	savepos MFPOS MEMORY_FILE
	goto STPOS MEMORY_FILE
	get NAME string MEMORY_FILE
	string NAME += .RXW
	goto MFPOS MEMORY_FILE
	
	set MEMORY_FILE2 binary \x52\x58\x57\x53\x30\x00\x00\x00\x00\x02\x00\x00\x00\x00\x00\x00\x46\x4F\x52\x4D\x20\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00
	
	putvarchr MEMORY_FILE2 0x24 UNK1 short
	putvarchr MEMORY_FILE2 0x26 UNK2 short
	putvarchr MEMORY_FILE2 0x28 UNK3 long
	putvarchr MEMORY_FILE2 0x2c UNK4 short
	putvarchr MEMORY_FILE2 0x2e FREQUENCY short
	putvarchr MEMORY_FILE2 0x38 SIZE long
	putvarchr MEMORY_FILE2 0x3c LOOP_POS long
	
	append
	log MEMORY_FILE2 OFFSET SIZE 1
	append
	
	math SIZE += 0x40
	log NAME 0 SIZE MEMORY_FILE2
next i

```


this quickbms scripts is a sloppy mess and i couldn't be bothered making it look even the least bit tidy, but it works at least 
It doesn't matter if you select either the .XWB or the .XWH file as the input, they will both work.

The output files can be played/converted with vgmstream, which I'm sure you'll find is very shagadelic 

If you have any problems or whatever, just lemme know & I'll be happy to help out.

PEACE brother
## Post #3
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-01-09T03:34:19+00:00
- Post Title: Phase Paradox [PS2] .XWB .ADPCM

Wow, that did it! 
RENIKRILL, thank you very much for writing this script!!! It extracted all tracks perfectly, absolutely awesome!
You really helped me out, thanks a lot man
## Post #4
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2012-01-09T04:00:23+00:00
- Post Title: Phase Paradox [PS2] .XWB .ADPCM

you're more than welcome
## Post #5
- Username: onlinedoghk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 09, 2016 11:16 pm
- Post datetime: 2016-10-09T16:53:30+00:00
- Post Title: Phase Paradox [PS2] .XWB .ADPCM

> Reply from RENIKRILL
>
> you're more than welcome

hello sir, 
Please help for ripping the music.  
i have been googling for a while and i found this post that talking about PS2 XWB format.
i am trying to extract xwb+xwh from a ps2 game - Bokura no Kazoku developed by Millennium Kitchen
The BGM is stored in \DATA\SOUND

i tried the following:
1. use the script from above for extracting. it resulted many rxw file but can not be played by vgmstream/MFAudio.
2. PS2cubemedia2 : it find SS2(Sony Audio File ) format audio and export only. can be played by MFAudio but very noisy.

the files are attached on this link:
[https://mega.nz/#F!vlQVRCJT!3nFJ5bIkOu7LK9myR5QzfQ](https://mega.nz/#F!vlQVRCJT!3nFJ5bIkOu7LK9myR5QzfQ)

Sorry for my poor English cause i have no idea what to do.
## Post #6
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2017-04-01T16:00:10+00:00
- Post Title: Phase Paradox [PS2] .XWB .ADPCM

The reason they don`t even play properly for the files used in that game is because it uses a different codec audio. I`ll see what I can do.

EDIT: Turns out the UNK4 variable of the script indicates the audio codec(0x200 representing the PlayStation ADPCM codec, and 0x100 representing ATRAC3, although if the UNK4 value is set to that number then figuring out the size field alone is going to be a tricky task). I`ll release a new revision of the script once I iron out these issues.
## Post #7
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2017-04-03T21:25:21+00:00
- Post Title: Phase Paradox [PS2] .XWB .ADPCM

...and done!

```
# original script by RENINKRILL(http://forum.xentax.com/viewtopic.php?p=64747#p64747)
# expanded by AnonBaiter to include the ATRAC3 codec used in later PS2 games developed/published by SCEI

open FDDE "XWH" 0
open FDDE "XWB" 1

math ATRAC3 = 0

idstring "RXWS"
get RXWSsz long   # minus 16byte header
get UNKNOWN long   # 0x200
get NULL long
idstring FORM
get FORMsz long   # -16
get UNKNOWN long   # 0x100
get NULL long
get STREAMS long

set FTXT_LOC long FORMsz
math FTXT_LOC += 0x20
goto FTXT_LOC
idstring FTXT
get FTXTsz long
get UNKNOWN long   # 0x100
get NULL long
savepos FTXT_LOC
log MEMORY_FILE FTXT_LOC FTXTsz
get STREAMS2 long MEMORY_FILE   # synonymous with 'STREAMS' value

goto 0x24

for i = 0 < STREAMS
	get UNK1 short   # 0x1c00
	get UNK2 short
	get UNK3 long   # 0x7f7f
	get UNK4 short
	get FREQUENCY short
	get NULL long
	get OFFSET long
	if UNK4 == 0x200
		get SIZE long
	else
		get UNK5 long
		xmath SIZE1 "UNK5 / 5"
	endif
	get LOOP_POS long
	
	get STPOS long MEMORY_FILE
	savepos MFPOS MEMORY_FILE
	goto STPOS MEMORY_FILE
	get NAME string MEMORY_FILE
	goto MFPOS MEMORY_FILE
	putarray 0 i OFFSET
	putarray 1 i SIZE1
	putarray 2 i UNK1
	putarray 3 i UNK2
	putarray 4 i UNK3
	putarray 5 i UNK4
	putarray 6 i FREQUENCY
	putarray 7 i NULL
	putarray 8 i OFFSET
	putarray 9 i LOOP_POS
	putarray 10 i NAME

	if UNK4 == 0x200
		callfunction RXW 1
	else
		math ATRAC3 = 1
	endif
next i

if ATRAC3 = 1
	get OFFSET asize 1
	putarray 0 i OFFSET
	for i = 0 < STREAMS
		getarray OFFSET 0 i
		getarray SIZE1 1 i
		getarray UNK1 2 i
		getarray UNK2 3 i
		getarray UNK3 4 i
		getarray UNK4 5 i
		getarray FREQUENCY 6 i
		getarray NULL 7 i
		getarray OFFSET 8 i
		getarray LOOP_POS 9 i
		getarray NAME 10 i
		math i + 1
		getarray SIZE 0 i
		math SIZE - OFFSET
		putarray 3 i SIZE
		xmath REMAINING "SIZE1 - SIZE"
		putarray 4 i REMAINING
		xmath FINAL_SIZE "SIZE1 - REMAINING"
		putarray 5 i FINAL_SIZE
		math FINAL_SIZE == SIZE
		callfunction RXW 1
		math i - 1
	next i
endif

startfunction RXW
	set MEMORY_FILE2 binary "\x52\x58\x57\x53\x30\x00\x00\x00\x00\x02\x00\x00\x00\x00\x00\x00\x46\x4F\x52\x4D\x20\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
	putvarchr MEMORY_FILE2 0x24 UNK1 short
	putvarchr MEMORY_FILE2 0x26 UNK4 short
	putvarchr MEMORY_FILE2 0x28 UNK3 long
	putvarchr MEMORY_FILE2 0x2c UNK4 short
	putvarchr MEMORY_FILE2 0x2e FREQUENCY short
	putvarchr MEMORY_FILE2 0x38 SIZE long
	putvarchr MEMORY_FILE2 0x3c LOOP_POS long
	append
	log MEMORY_FILE2 OFFSET SIZE 1
	append
	string NAME += ".rxw"

	math SIZE += 0x40
	log NAME 0 SIZE MEMORY_FILE2
endfunction
```
This was all I had to do based on onlinedoghk`s sample.
## Post #8
- Username: onlinedoghk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 09, 2016 11:16 pm
- Post datetime: 2017-07-20T18:00:25+00:00
- Post Title: Phase Paradox [PS2] .XWB .ADPCM

I was pleasantly surprised and thanks for your help AnonBaiter.   

i used the new script. it can extract some of RXW format files.
when i try to play it on foobar / mfaudio .
it still come with crackling noise same with the first try.

BUT , i found that vgmstram([https://github.com/kode54/vgmstream/blo ... ps2_rxws.c](https://github.com/kode54/vgmstream/blob/master/src/meta/ps2_rxws.c))  has been update. it support SCEI games.

However it can play the first track of XWB format only?(i guess).
there should have other sound in this file? 

Here is the properties from playing bgm.xwb:
----------------------------------------------------
Duration 2:19(1 track only)
Sample Rate 48000Hz
channels 2
bits per sample 16
bitrate 2823kbps
codec ATRAC3
Encoding lossless
-------------Other--------------
Layout flat
metadata source Sony RXWS header
Number of streams 40
stream total samples 6649343
---------------------------------------------------

I have upload a whole SOUND file from the disc for your information. 
Many Thanks.
