## Post #1
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2019-08-07T08:19:54+00:00
- Post Title: Summoner 2 (PS2) *.VPP

Hi fellow rippers (and anyone else who'd like to help me out), may I ask you to look into [samples of Volition VPP archives](https://drive.google.com/open?id=1E6znWPR5tK0QoV6PfCnDGDo7QDT2n47x) ([mirror](https://www.sendspace.com/file/1l5sln))? They're from Summoner 2, a PS2 exclusive title, and the newest rfguerrilla.bms can't handle them: QuickBMS reports "divide by zero" on every *.VPP file.
Goodbye and thanks in advance!

PS. I also tried Game Extractor & Novasoft Extractor (both can open Red Faction 1 (PC ver.) VPPs but not these) then gibbed.volition_1.0.0 pack but still nothing.
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-08-07T16:49:41+00:00
- Post Title: Summoner 2 (PS2) *.VPP

Try this script - it should do the job!


# Summoner PS2 VPP extract

ComType zlib_noerror

Goto 0x3c
Get ENTRIES Long

Goto 0x4C
Get DATA_SIZE1 Long
Get DATA_SIZE2 Long

PutVarChr MEMORY_FILE DATA_SIZE2 0
Log MEMORY_FILE 0 0
CLog MEMORY_FILE 0x1800 DATA_SIZE1 DATA_SIZE2

Set FILE_ENTRIES 0x800
Set FILE_NAMES 0x1000

For A = 1 to ENTRIES

	Goto FILE_ENTRIES

	Get FNAME_OFF Long
	Get OFFSET Long
	Get JUNK Long
	Get SIZE Long

	Math FNAME_OFF + FILE_NAMES
	Goto FNAME_OFF
	Get FILENAME String

	Log FILENAME OFFSET SIZE -1

	Math FILE_ENTRIES + 0x1C

Next A
## Post #3
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2019-08-08T11:06:20+00:00
- Post Title: Summoner 2 (PS2) *.VPP

I don't know, I get this error on both MUSIC.VPP & SOUNDS.VPP and nothing is extracted.
BTW what ver. of quickbms.exe do you use?
Bye!
[sum.jpg](https://xentaxbackup.github.io/file/16580_sum.jpg)
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-08-08T16:13:45+00:00
- Post Title: Summoner 2 (PS2) *.VPP

Hi.

I have the same version of QuicmBKS as you, but I've just noticed what the issue is.  I was only looking at one of the other files (which are compressed), and not the MUSIC file, so I wasn't accounting for uncompressed archives, which store the info slightly differently.

Hopefully this script should work correctly now for all those VPP archives.  I couldn't test it properly on MUSIC as I only have a partial file, so please let me know if it still doesn't work.


# Summoner VPP extract

ComType zlib_noerror

Goto 0x3c
Get ENTRIES Long

Goto 0x4C
Get DATA_SIZE1 Long
Get DATA_SIZE2 Long

If DATA_SIZE1 <> 0xFFFFFFFF
	PutVarChr MEMORY_FILE DATA_SIZE2 0
	Log MEMORY_FILE 0 0
	CLog MEMORY_FILE 0x1800 DATA_SIZE1 DATA_SIZE2
Endif

Set FILE_ENTRIES 0x800
Set FILE_NAMES 0x1000
Set OFFSET2 0x1800

For A = 1 to ENTRIES

	Goto FILE_ENTRIES

	Get FNAME_OFF Long
	Get OFFSET Long
	Get JUNK Long
	Get SIZE Long

	Math FNAME_OFF + FILE_NAMES
	Goto FNAME_OFF
	Get FILENAME String

	If DATA_SIZE1 <> 0xFFFFFFFF
		Log FILENAME OFFSET SIZE -1
	Else
		Log FILENAME OFFSET2 SIZE 0
		Math OFFSET2 + SIZE
	Endif

	Math FILE_ENTRIES + 0x1C

Next A
## Post #5
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2019-08-09T10:36:02+00:00
- Post Title: Summoner 2 (PS2) *.VPP

Well it seems to unpack MUSIC.VPP but not SOUNDS.VPP; to be precise it (QuickBMS.exe) extracts some files out of SOUNDS.VPP but they all have names like 0000001b.dat or 00000003.ia_, sometimes the program even makes me type in file names (WTH?!).
Maybe you'd like to try working with complete SOUNDS.VPP? It's 126 МBs but I hope it's not such a bother to download a file of this size these days. Am I right?
So long!
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-08-09T15:44:26+00:00
- Post Title: Summoner 2 (PS2) *.VPP

Yes, I should be able to use that whole SOUNDS file, no problem.  It sounds like they've messed with the format for different types of files, so what works for one doesn't necessarily work for others.  But if you can upload the complete file it would be useful.
## Post #7
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2019-08-09T16:39:11+00:00
- Post Title: Summoner 2 (PS2) *.VPP

[Here you can get both untouched archives](https://mega.nz/#!UVc1RQTD!pEgO4sMHM9Eue8Dai0uNT5URXvr-MXE9w7VAkn3dRNM), I included MUSIC.VPP because I'm not so sure that extraction of it went smoothly either: I can't find correct interleave value for lots of tracks & many of those can't even be played as PS2 ADPCM (can be another codec but it's still rather unlikely).
Thanks in advance & good luck!
## Post #8
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-08-09T17:28:40+00:00
- Post Title: Summoner 2 (PS2) *.VPP

Thanks.  Those full files helped.  I think I've cracked it this time.  Third time lucky, hopefully.  I was making assumptions about the format that were wrong.  Compressed and uncompressed archives are treated slightly differently.  The uncompressed ones are aligned on an 0x800 byte boundary, which I needed to take account of to get the data extracted from the correct offset.

The extracted MUSIC files (*.vmu) have 12 bytes of data before the PS ADPCM data.  I assume this is some information about the file (sample rate, channels).  I'm not sure exactly how that info is stored, but the music seems to be stereo, 22,050 Hz, Interleave 0x4000.

The SOUNDS files (*.vse) have no additional data at the start and are PS ADPCM, mono, 22,050 Hz.  There are over 4,000 of them so I haven't checked them all.

So, fingers crossed this will work correctly for you now!


# Summoner 2 VPP extract

ComType zlib_noerror

Goto 0x3c
Get ENTRIES Long

Goto 0x44
Get TABLE1_SIZE Long
Get TABLE2_SIZE Long
Set MOD1_VALUE TABLE1_SIZE
Math MOD1_VALUE % 0x800
Set MOD2_VALUE TABLE2_SIZE
Math MOD2_VALUE % 0x800

Goto 0x4C
Get DATA_SIZE1 Long
Get DATA_SIZE2 Long

If DATA_SIZE1 <> 0xFFFFFFFF
	PutVarChr MEMORY_FILE DATA_SIZE2 0
	Log MEMORY_FILE 0 0
	CLog MEMORY_FILE 0x1800 DATA_SIZE1 DATA_SIZE2
Endif

Set FILE_ENTRIES 0x800
Set FILE_NAMES FILE_ENTRIES
Math FILE_NAMES + TABLE1_SIZE

If MOD1_VALUE > 0
	XMath FILE_NAMES "FILE_NAMES + 0x800 - MOD1_VALUE"
Endif

Set OFFSET2 FILE_NAMES
Math OFFSET2 + TABLE2_SIZE

If MOD2_VALUE > 0
	XMath OFFSET2 "OFFSET2 + 0x800 - MOD2_VALUE"
Endif


For A = 1 to ENTRIES

	Goto FILE_ENTRIES

	Get FNAME_OFF Long
	Get OFFSET Long
	Get JUNK Long
	Get SIZE Long

	Math FNAME_OFF + FILE_NAMES
	Goto FNAME_OFF
	Get FILENAME String

	If DATA_SIZE1 <> 0xFFFFFFFF
		Log FILENAME OFFSET SIZE -1
	Else
		Log FILENAME OFFSET2 SIZE 0
		Math OFFSET2 + SIZE
		XMath MOD3_VALUE "OFFSET2 % 0x800"

		If MOD3_VALUE > 0
			XMath OFFSET2 "OFFSET2 + 0x800 - MOD3_VALUE"
		Endif
	Endif

	Math FILE_ENTRIES + 0x1C

Next A
## Post #9
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2019-08-10T13:28:56+00:00
- Post Title: Summoner 2 (PS2) *.VPP

I can't thank you enough man, all BGMs & CS tracks work now (basically everything from MUSIC.VPP) but unfortunately I'm having some difficulties playing a few *.VSE files (musician_*.VSE or odoni_pet_music*.VSE to name some of those). If you looked into them I'd highly appreciate it!
All the best!
## Post #10
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-08-10T13:43:04+00:00
- Post Title: Summoner 2 (PS2) *.VPP

No problem!

I've just used my BMS script on the SOUNDS archive.  The musician_*.vse files play perfectly for me as mono, 22050 Hz, PS ADPCM.  I used GENH to test them and they all worked ok.  An example attached of both the .vse and the GENH version I created, so you can compare the original file with what you get from the script (although it should be identical).
[musician_song_of_ mourning.zip](https://xentaxbackup.github.io/file/16588_musician_song_of_ mourning.zip)
## Post #11
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2019-08-11T11:44:56+00:00
- Post Title: Summoner 2 (PS2) *.VPP

Nevermind, I've got it all sorted out and it was just a stupid mistake on my end while I was working with those *.vse files; they play perfectly for me now.
Thanks nonetheless & bye!
## Post #12
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2019-09-01T01:45:51+00:00
- Post Title: Summoner 2 (PS2) *.VPP

The Punisher also uses these formats, but this doesn't seem to work for it.
[http://www.mediafire.com/file/ebano4qms ... E.zip/file](http://www.mediafire.com/file/ebano4qms6tco9v/VOICE.zip/file)
## Post #13
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-09-01T10:25:30+00:00
- Post Title: Summoner 2 (PS2) *.VPP

That Punisher VPP archive is a slightly different (and simpler) format, so you'll need a different script.  Try this one.

All of the files seem to be mono, 22050 Hz, PSX audio.


# Punisher (PS2) - VPP extract
# By Dave

Goto 0x0008
Get ENTRIES Long
Goto 0x0010
Get FILE_TABLE Long

XMath DATA_START "(ENTRIES * 0x20) + 0x800"
XMath REMAINDER "DATA_START % 0x800"

If REMAINDER > 0
	XMath DATA_START "DATA_START + 0x800 - REMAINDER"
Endif

For A = 1 to ENTRIES

	Goto FILE_TABLE
	GetDString FILENAME 0x18
	Get SIZE1 Long
	Get SIZE2 Long

	Log FILENAME DATA_START SIZE1

	Math DATA_START + SIZE1
	XMath REMAINDER "DATA_START % 0x800"
	If REMAINDER > 0
		XMath DATA_START "DATA_START + 0x800 - REMAINDER"
	Endif

	Math FILE_TABLE + 0x20

Next A
## Post #14
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2019-09-02T18:01:40+00:00
- Post Title: Summoner 2 (PS2) *.VPP

[This should work too.](http://aluigi.org/bms/rfguerrilla.bms)
Bye 41hc1!
## Post #15
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2019-09-03T06:32:15+00:00
- Post Title: Summoner 2 (PS2) *.VPP

Thanks, the one by Dave works. The Red Faction one actually doesn't work for Punisher. How can I extract the .vse audio for Punisher?
[http://www.mediafire.com/file/5679zwud7 ... e.zip/file](http://www.mediafire.com/file/5679zwud7b8fwca/vse.zip/file)
## Post #16
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-09-03T15:56:13+00:00
- Post Title: Re: Summoner 2 (PS2) *.VPP

All of the .vse files in that Punisher VOICE.VPP archive are headerless PSX audio, so you can use GENH with the values I mentioned, or create a TXTH file to play them in Foobar.  If you want a TXTH file I've probably still got a copy somewhere.
## Post #17
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2019-09-04T21:38:35+00:00
- Post Title: Re: Summoner 2 (PS2) *.VPP

Do you still have a TXTH?
## Post #18
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-09-06T22:50:29+00:00
- Post Title: Re: Summoner 2 (PS2) *.VPP

Yes, sorry.  Here it is:

codec = PSX
sample_rate = 22050
channels = 1
start_offset = 0x0000
num_samples = data_size

If you save that as .vgmstgream.txth and rename all the .vse files to .vgmstream, they will play.
## Post #19
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2019-09-07T04:29:41+00:00
- Post Title: Re: Summoner 2 (PS2) *.VPP

Thank you. This is working just fine. I also realized the .vmu format is used here in Punisher as well, but it also seems to be slightly different?
[http://www.mediafire.com/file/zt92fix7u ... u.zip/file](http://www.mediafire.com/file/zt92fix7u384dnz/vmu.zip/file)
## Post #20
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2019-09-14T04:36:00+00:00
- Post Title: Re: Summoner 2 (PS2) *.VPP

Hi, you seem to have wrong d_club_1 file: it's supposed to have *.vse extension & much smaller size, this is what I got when I ripped VGM from the game using rfguerrilla.bms. Get [my version of d_club_1.vse](https://www.sendspace.com/file/u637jf) & above *.TXTH should work for it.

As for other samples - try this TXTH out:

codec = PSX
interleave = 0x4000
sample_rate = 22050
channels = 2
start_offset = 0xc
num_samples = data_size

BTW if you wanna get BGM you can get my gamerip with mono tracks separated from stereo ones & assigned (approximate) frequency values. Send a PM if you're interested.

Later!
## Post #21
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2019-09-15T15:44:26+00:00
- Post Title: Re: Summoner 2 (PS2) *.VPP

Thanks, this is working just fine also. That d_club_1 is from the demo, that's why it has .vmu extension.
## Post #22
- Username: marcoxD95
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 27, 2019 5:14 am
- Post datetime: 2023-09-13T06:07:09+00:00
- Post Title: Re: Summoner 2 (PS2) *.VPP

I have a problem too that I thought would fit best into this thread here.

Basically I have extracted the music from Red Faction 2 (PS2) which was in .VPP files as well.
I ended up with .VMU files. They seem to be some kind of PSX SS2 audio file, probably similar to stuff like Summoner 2 here.

I also found a really old thread about it which was from 2012 which makes these files playable BUT there is one problem...
They do not play as they should and sound garbled and like the header isnt entirely correct.
Here is the thread for reference: [viewtopic.php?p=74188&hilit=red+faction+2+vmu](https://forum.xentax.com/viewtopic.php?p=74188&hilit=red+faction+2+vmu)

Ive tried multiple tools and ways to make them play properly but couldnt find anything out.

Here are the files in question for research:
[https://disk.yandex.com/d/CH0Im2XkSixsZg](https://disk.yandex.com/d/CH0Im2XkSixsZg)

Here is also a way smaller version with only one sample .VMU for people who are bandwith limited:
[https://disk.yandex.com/d/TOxf-PG1wNP-4Q](https://disk.yandex.com/d/TOxf-PG1wNP-4Q)
