## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-08-24T11:10:44+00:00
- Post Title: headerless ADPCM

Hi there!

I have some headerless ADPCM files and I'm really struggeling to get them to play. Tried different offsets and codecs with GENH but to no avail. Does anyone have a clue which properties these files have?
Samples: [http://www.putlocker.com/file/F5CF683BDDD40779](http://www.putlocker.com/file/F5CF683BDDD40779)

Regards, Timo
## Post #2
- Username: Molt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 19, 2013 10:57 pm
- Post datetime: 2013-08-24T17:06:07+00:00
- Post Title: headerless ADPCM

As far as I can see, bytes 4-8 give the length of the whole file (I guess you already know that, though) and until offset 46544, they are identical (except for the 4 length-bytes).

This is the point where the contents change:

```
46528	99 01 22 BA 5C C0 00 40 00 00 00 00 00 00 00 00
46544	7F F7 7F F7 61 8D 84 1C 92 28 AA 52 BB 85 2A C1

INTROSEQ
46528	99 01 22 BA 5C C0 00 40 00 00 00 00 00 00 00 00
46544	77 75 97 9C 30 12 00 A8 FD BB BD 10 73 57 CC BD
```


Could you please check if you have any files of that format which have different contents before 46544?

Regards
Molt
## Post #3
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-08-24T19:44:51+00:00
- Post Title: headerless ADPCM

I've imported them into Audacity as raw, VOX ADPCM files and although it was not perfect, I heard few sounds there. Like walking, thunders, shooting, cat, etc.
I tried sample rate 44.1kHz, but it was bit fast, but 32 kHz sounds better.

My try

[http://www.sendspace.com/file/hlk9re](http://www.sendspace.com/file/hlk9re)
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-08-25T12:25:03+00:00
- Post Title: headerless ADPCM

Yes, the files start out the same (shouldn't matter though). They are audio containers from Hitman 2 for Xbox. The TOC is in *.WHD files, but they don't seem to contain information about the interleave or codec.
I've also tried the raw import of Audacity but the problem is that it doesn't support raw import for other ADPCM codecs. I've searched high and low but didn't find any program that has that feature. So all you can do is try out different settings of GENH. Strangely I didn't encounter a single setting that produced anything besides static noise. Does anybody have an idea what's the closest stereo relative to VOX ADPCM?
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-08-25T13:47:17+00:00
- Post Title: headerless ADPCM

LOL, this ist simply XBOX ADPCM! How the hell didn't I recognize this...
Will write an extractor for the wav/whd pairs later. Seems like this is the same engine like Kane & Lynch or Condemned, so the script should also apply to these games.
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-08-25T14:24:06+00:00
- Post Title: headerless ADPCM

Glacier engine - WHD/WAV pairs

Games like the Hitman series, Freedom Fighters or Kane & Lynch. You will need to put all whd/wav pairs as well as the streams.wav (if available) into the same folder.
Not all tested, though. So if you have problems with any of the Glacier games, post here.

```
# needs the streams.wav in the same folder as the whd/wav pair(s)
# tested with Hitman 2: Silent Assassin (Xbox, PS2)
# (c) 2013-08-30 by AlphaTwentyThree of XeNTaX
# script for QuickBMS http://quickbms.aluigi.org

open FDDE WHD 0
open FDDE WAV 1
open FDSE "streams.wav" 2 EXISTS
if EXISTS == 0
	open FDSE "STREAMS.WAV" 2 EXISTS
endif
get TOCSIZE long 0
get WHDSIZE long 0
if WHDSIZE == 0x18
	cleanexit
endif
get UNK longlong 0
do
	get NAME string 0
	savepos MYOFF 0
	math MYOFF x= 4
	goto MYOFF 0
	get UNK long 0
	get UNK long 0
	get CODEC threebyte 0
	get FILE byte 0
	get FREQ long 0
	get BITS long 0
	get UNK long 0
	get SIZE long 0
	get CH long 0
	get OFFSET long 0
	get UNK long 0
	get INTERLEAVE long 0
	get UNK long 0
	savepos MYOFF 0
	if FILE == 0
		if CODEC == 0x69
			string NAME += ".lwav"
			callfunction XADP 1
		elif CODEC == 1
			set BLOCKALIGN 1
			callfunction PCM_1 1
		elif CODEC == 0x12
			string NAME += ".genh"
			set CODEC 9
			if CH == 1
				set INTERLEAVE 0
			endif
			callfunction GENH 1
		else
			print "Error: unknown codec. Aborting..."
			cleanexit
		endif
	elif FILE == 0x80
		if EXISTS == 1
			set BLOCKALIGN 1
			callfunction PCM_2 1
		endif
	endif
while MYOFF < TOCSIZE

startfunction XADP
	set MEMORY_FILE binary "\x52\x49\x46\x46\x18\x51\xa3\x0\x57\x41\x56\x45\x66\x6d\x74\x20\x14\x0\x0\x0\x69\x0\x2\x0\x44\xac\x0\x0\xcc\xc1\x0\x0\x48\x0\x4\x0\x2\x0\x40\x0\x64\x61\x74\x61\xf0\x50\xa3\x0"
	set RIFFSIZE SIZE
	math RIFFSIZE += 0x28
	putVarChr MEMORY_FILE 0x04 RIFFSIZE long
	putVarChr MEMORY_FILE 0x16 CH byte
	putVarChr MEMORY_FILE 0x18 FREQ long
	set VAR1 0x3073
	math VAR1 *= CH
	if FREQ == 48000
		math VAR1 *= 44100
	else
		math VAR1 *= FREQ
	endif
	math VAR1 /= 22050
	putVarChr MEMORY_FILE 0x1c VAR1 long	
	set VAR2 0x24
	math VAR2 *= CH
	putVarChr MEMORY_FILE 0x20 VAR2 short
	putVarChr MEMORY_FILE 0x2c SIZE long
	append
	log MEMORY_FILE OFFSET SIZE 1
	append
	if NAME == ""
		get NAME basename
		string NAME += ".lwav"
	endif
	get SIZE asize MEMORY_FILE
	log NAME 0 SIZE MEMORY_FILE
endfunction

startfunction PCM_1
	set PRE SIZE
	math PRE += 0x2c
	putVarChr MEMORY_FILE PRE 0
	log MEMORY_FILE 0 0
	set MEMORY_FILE binary "\x52\x49\x46\x46\x20\xC0\xB1\x00\x57\x41\x56\x45\x66\x6D\x74\x20\x10\x00\x00\x00\x01\x00\x02\x00\x44\xAC\x00\x00\x10\xB1\x02\x00\x04\x00\x10\x00\x64\x61\x74\x61\xFC\xBF\xB1\x00"
	append
	log MEMORY_FILE OFFSET SIZE 1
	append
	set RIFFSIZE SIZE
	math RIFFSIZE += 36
	set AVGBYTES FREQ
	if CODEC != 2
		math AVGBYTES *= BLOCKALIGN
	endif
	
	putvarchr MEMORY_FILE 0x04 RIFFSIZE long
	putvarchr MEMORY_FILE 0x14 CODEC short
	putvarchr MEMORY_FILE 0x16 CH short
	putvarchr MEMORY_FILE 0x18 FREQ short
	putvarchr MEMORY_FILE 0x1c AVGBYTES long
	putvarchr MEMORY_FILE 0x20 BLOCKALIGN short
	putvarchr MEMORY_FILE 0x22 BITS short
	putvarchr MEMORY_FILE 0x28 SIZE long
	if NAME == ""
		get NAME basename
		string NAME += ".wav"
	endif
	get SIZE asize MEMORY_FILE
	log NAME 0 SIZE MEMORY_FILE
endfunction

startfunction PCM_2
	set PRE SIZE
	math PRE += 0x2c
	putVarChr MEMORY_FILE PRE 0
	log MEMORY_FILE 0 0
	set MEMORY_FILE binary "\x52\x49\x46\x46\x20\xC0\xB1\x00\x57\x41\x56\x45\x66\x6D\x74\x20\x10\x00\x00\x00\x01\x00\x02\x00\x44\xAC\x00\x00\x10\xB1\x02\x00\x04\x00\x10\x00\x64\x61\x74\x61\xFC\xBF\xB1\x00"
	append
	log MEMORY_FILE OFFSET SIZE 2
	append
	set RIFFSIZE SIZE
	math RIFFSIZE += 36
	set AVGBYTES FREQ
	if CODEC != 2
		math AVGBYTES *= BLOCKALIGN
	endif
	
	putvarchr MEMORY_FILE 0x04 RIFFSIZE long
	putvarchr MEMORY_FILE 0x14 CODEC short
	putvarchr MEMORY_FILE 0x16 CH short
	putvarchr MEMORY_FILE 0x18 FREQ short
	putvarchr MEMORY_FILE 0x1c AVGBYTES long
	putvarchr MEMORY_FILE 0x20 BLOCKALIGN short
	putvarchr MEMORY_FILE 0x22 BITS short
	putvarchr MEMORY_FILE 0x28 SIZE long
	if NAME == ""
		get NAME basename
		string NAME += ".wav"
	endif
	get SIZE asize MEMORY_FILE
	log NAME 0 SIZE MEMORY_FILE
endfunction

startfunction GENH
	set SAMPLES SIZE
	math SAMPLES *= 8
	math SAMPLES /= BITS

	set FSIZE SIZE
	math FSIZE += 0x1000
	putVarChr MEMORY_FILE FSIZE 0
	log MEMORY_FILE 0 0
	putVarChr MEMORY_FILE 0 0x484e4547 long
	putVarChr MEMORY_FILE 0x4 CH long
	putVarChr MEMORY_FILE 0x8 INTERLEAVE long
	putVarChr MEMORY_FILE 0xc FREQ long
	putVarChr MEMORY_FILE 0x10 0xffffffff long
	putVarChr MEMORY_FILE 0x14 SAMPLES long
	putVarChr MEMORY_FILE 0x18 CODEC long
	putVarChr MEMORY_FILE 0x1c 0x1000 long # offset; == stream start if no header
	putVarChr MEMORY_FILE 0x20 0x1000 long
	putVarChr MEMORY_FILE 0x300 FSIZE long
	putVarChr MEMORY_FILE 0x304 0x32304756 long
	putVarChr MEMORY_FILE 0xfff 0 byte
	math FSIZE -= 0x1000
	append
	log MEMORY_FILE OFFSET FSIZE 1
	append
	get SIZE asize MEMORY_FILE
	log NAME 0 SIZE MEMORY_FILE
endfunction
```
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-08-25T15:04:31+00:00
- Post Title: headerless ADPCM

Made some more changes - the script now supports the extraction of the streams.wav-internals too (dialogue and music).   
The streams.wav needs to be located in the same folder as the *.whd/*.wav pair(s).
## Post #8
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-08-25T19:01:55+00:00
- Post Title: headerless ADPCM

KL2 doesn't have a streams.wav file, do you still have the older script anywhere?
## Post #9
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-08-25T21:21:45+00:00
- Post Title: headerless ADPCM

> Reply from Pepper
>
> KL2 doesn't have a streams.wav file, do you still have the older script anywhere?
It should also work without the streams.wav I think.
Will update the script with PS2 ADPCM soon.
## Post #10
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-08-25T21:24:36+00:00
- Post Title: headerless ADPCM

> Reply from AlphaTwentyThree
>
> Pepper wrote:KL2 doesn't have a streams.wav file, do you still have the older script anywhere?
It should also work without the streams.wav I think.
Will update the script with PS2 ADPCM soon.
Doesn't seem to. errors out with a no such file or directory on streams.wav
## Post #11
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-08-26T08:12:05+00:00
- Post Title: headerless ADPCM

Ah right, will change later.
## Post #12
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-08-29T15:57:39+00:00
- Post Title: headerless ADPCM

Fixed. Just put an "EXISTS" behind the open command.
## Post #13
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-08-30T20:59:41+00:00
- Post Title: headerless ADPCM

Added support for games that use IMA ADPCM, e.g. the PS2 version of Hitman 2!
## Post #14
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-09-02T20:55:05+00:00
- Post Title: headerless ADPCM

Really great work! wondering what codec KL/2 uses and if it can be supported? I'm PMing samples.
