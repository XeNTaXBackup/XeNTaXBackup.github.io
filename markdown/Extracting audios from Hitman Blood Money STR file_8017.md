## Post #1
- Username: maurocio
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jan 27, 2010 3:45 am
- Post datetime: 2012-01-09T17:39:41+00:00
- Post Title: Extracting audios from Hitman Blood Money STR file

Hi all,

I try to extract all audios on file pc_eng.str file from Hitman Blood money, but the most of files has a type a unknow conversion.

I manage a program (attached on post) to explore str file and extract files. Files appear like wav, but files are not wav. This app extract all files but u only can play a few files that are ogg rest of files has a conversion/compresion. 

I know that I can use program towav (this extract files and do a conversion on wav files, anyone knowns that conversion is?)

Could anyone help to analyze this files?
many thanks.
If you need I can attach a wav file or str hitman file.

To extract files from str file uses right button on file, file will extracted on temp folder

Note: Is possible that this program works with Kane and Lynch
[str.zip](https://xentaxbackup.github.io/file/4969_str.zip)
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-01-11T18:14:08+00:00
- Post Title: Extracting audios from Hitman Blood Money STR file

You should upload some of these unplayable files to take a look at.
## Post #3
- Username: maurocio
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jan 27, 2010 3:45 am
- Post datetime: 2012-01-12T07:53:35+00:00
- Post Title: Extracting audios from Hitman Blood Money STR file

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-01-12T13:44:38+00:00
- Post Title: Extracting audios from Hitman Blood Money STR file

I'm currently writing a script for this particular file. Some of these are plain wav, others ogg as you already metioned, others are headerless IMA adpcm with information provided. I'll try to automatically add valid headers to the individual files or automatically rename them to ogg.
I'll post here again later.
## Post #5
- Username: maurocio
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jan 27, 2010 3:45 am
- Post datetime: 2012-01-12T13:53:33+00:00
- Post Title: Extracting audios from Hitman Blood Money STR file

Sorry, I don't put a dialog message to choose the path for extract. You need to put a folder named 'temp' on same folder of program to extract files on temp folder.

Thanks
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-01-12T14:16:12+00:00
- Post Title: Extracting audios from Hitman Blood Money STR file

Ok, I've quickly written a script that extracts the files including the header information from the source file. I named all files *.rwav (raw wav) for later postprocessing. For this purpose I've just constructed a header consisting the "RWAV" idstring, the data start offset and the header from the str file.
I'll get to the postprocessing later on.
Here's the script so far:

```
goto 0x10
get INFO long
get FILES long
get HEADERSIZE long
goto INFO
for i = 1 <= FILES
	get FILENUMBER long
	get ZERO long
	get OFFSET long
	get ZERO long
	get SIZE long
	get ZERO long
	get INFOPOS long
	get ZERO long
	get INFOLENGTH long
	get UNK long
	get NAMEL long
	get ZERO long
	get NAMEPOS long
	get ZERO long
	get UNK long
	get UNK long
	get ZERO long
	get ZERO long
	savepos MYOFF
	goto NAMEPOS
	getDstring NAME NAMEL
	log MEMORY_FILE 0 0
	set HEADERSIZE INFOLENGTH
	math HEADERSIZE += 8
	PutVarChr MEMORY_FILE 0 0x56415752 long # RWAV
	PutVarChr MEMORY_FILE 4 HEADERSIZE long
	append
	log MEMORY_FILE INFOPOS INFOLENGTH
	log MEMORY_FILE OFFSET SIZE
	append
	get SIZE asize MEMORY_FILE
	string NAME += ".rwav"
	log NAME 0 SIZE MEMORY_FILE
	goto MYOFF
next i
```
## Post #7
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2012-01-12T21:20:54+00:00
- Post Title: Extracting audios from Hitman Blood Money STR file

thanks for this!
## Post #8
- Username: maurocio
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jan 27, 2010 3:45 am
- Post datetime: 2012-01-13T21:11:26+00:00
- Post Title: Extracting audios from Hitman Blood Money STR file

Woahhhh!!

AlphaTwentyThree you're a genius!!!!

I waste two weeks on try to get info about str file and try to explore this correct, and you only need a few a hours.
## Post #9
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-01-13T21:25:26+00:00
- Post Title: Extracting audios from Hitman Blood Money STR file

Well, not finished yet - the IMA adpcm format is a bit tricky...
Be sure to leave a "thanks" while I'm at it.
## Post #10
- Username: maurocio
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jan 27, 2010 3:45 am
- Post datetime: 2012-01-14T19:28:58+00:00
- Post Title: Extracting audios from Hitman Blood Money STR file

sure.

Do you have decode info values on file?

I'll try to decode info on file but only see a value that indicate frencuency on Hz

Info

Unk1 long
Unk2 long
Unk3 long (maybe indicate 1 mono 2, stereo)
Frencuency_on_hz long
Unk4 long (maybe bits)
Unk5 long
Unk6 long


I'm continuing analizing this info.

Thanks
## Post #11
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-02-17T20:49:15+00:00
- Post Title: Extracting audios from Hitman Blood Money STR file

Ok, finished the script after a while. Had so find a working IMA ADPCM header first. Apparently I found one. 
So here's the script to post-process the *.rwav files. Resulting  *.lwav files can be played with the vgmstream plugin for Winamp.

```
# (c) 2012-02-17 by AlphaTwentyThree of XeNTaX

idstring "RWAV"
get OFFSET long
get SIZE asize
math SIZE -= OFFSET
get TYPE long
get UNK long
get CH long
get FREQ long
get BITS long
	
if TYPE == 2 # uncompressed PCM, 0x18 header
	set TYPE "WAV"
elif TYPE == 0x11
	set TYPE "WAV"
elif TYPE == 3 # IMA ADPCM, 0x20 header
	set TYPE "IMA"
elif TYPE == 4 # ogg
	set TYPE "OGG"
endif

if TYPE == "WAV"
	get BLOCKALIGN long
	callfunction PCM 1
	get SIZE asize MEMORY_FILE
	get NAME basename
	string NAME += ".wav"
	log NAME 0 SIZE MEMORY_FILE
elif TYPE == "IMA"
	get INTERLEAVE long
	get UNK long
	callfunction IMA 1
	get SIZE asize MEMORY_FILE
	get NAME basename
	string NAME += ".lwav"
	log NAME 0 SIZE MEMORY_FILE
elif TYPE == "OGG"
	get NAME basename
	string NAME += ".ogg"
	log NAME OFFSET SIZE
endif

startfunction PCM
	set PRE SIZE
	math PRE += 0x2c
	putVarChr MEMORY_FILE PRE 0
	log MEMORY_FILE 0 0
	set MEMORY_FILE binary "\x52\x49\x46\x46\x00\x00\x00\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x64\x61\x74\x61\xff\xff\xff\xff"
	append
	log MEMORY_FILE OFFSET SIZE
	append
	set RIFFSIZE SIZE
	math RIFFSIZE += 36
	set AVGBYTES FREQ
	math AVGBYTES *= BLOCKALIGN

	putvarchr MEMORY_FILE 4 RIFFSIZE long
	putvarchr MEMORY_FILE 20 1 short          # wFormatTag: Microsoft PCM Format (0x0001)
	putvarchr MEMORY_FILE 22 CH short   # wChannels
	putvarchr MEMORY_FILE 24 FREQ long   # dwSamplesPerSec
	putvarchr MEMORY_FILE 28 AVGBYTES long    # dwAvgBytesPerSec
	putvarchr MEMORY_FILE 32 BLOCKALIGN short # wBlockAlign
	putvarchr MEMORY_FILE 34 BITS short       # wBitsPerSample
	putvarchr MEMORY_FILE 40 SIZE long
endfunction

startfunction IMA
	set PRE SIZE
	math PRE += 0x2c
	putVarChr MEMORY_FILE PRE 0
	log MEMORY_FILE 0 0
	set MEMORY_FILE binary "\x52\x49\x46\x46\x28\xCC\x0B\x00\x57\x41\x56\x45\x66\x6D\x74\x20\x14\x00\x00\x00\x11\x00\x01\x00\x44\xAC\x00\x00\x94\x83\x01\x00\x00\x04\x04\x00\x02\x00\x40\x00\x64\x61\x74\x61\x00\xCC\x0B\x00"
	set RIFFSIZE SIZE
	math RIFFSIZE += 0x28
	putVarChr MEMORY_FILE 0x4 RIFFSIZE long
	putVarChr MEMORY_FILE 0x16 CH short
	putVarChr MEMORY_FILE 0x18 FREQ long
	putVarChr MEMORY_FILE 0x20 INTERLEAVE short
	putVarChr MEMORY_FILE 0x2C SIZE long
	append
	log MEMORY_FILE OFFSET SIZE
	append
endfunction
```
## Post #12
- Username: maurocio
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jan 27, 2010 3:45 am
- Post datetime: 2012-02-21T11:54:31+00:00
- Post Title: Extracting audios from Hitman Blood Money STR file

woah!!!!! Amazing!!!!

Thanks 4 your work
## Post #13
- Username: master20
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 13, 2012 3:35 am
- Post datetime: 2012-04-12T20:23:59+00:00
- Post Title: Extracting audios from Hitman Blood Money STR file

sorry.how can i use this script? explain please
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-04-12T21:53:18+00:00
- Post Title: Extracting audios from Hitman Blood Money STR file

[viewtopic.php?f=28&t=1270](http://forum.xentax.com/viewtopic.php?f=28&t=1270) Please review the new forum rules everyone.
## Post #15
- Username: InnocentSam2
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Apr 05, 2012 9:06 pm
- Post datetime: 2013-04-05T22:47:13+00:00
- Post Title: Extracting audios from Hitman Blood Money STR file

Your scripts work fine however the file I output gets clipped off at the end and start with a large amount of static briefly. I used the vgmstream plugin for VLC and the vgmstream "test.exe" but they both produce the same sound.
