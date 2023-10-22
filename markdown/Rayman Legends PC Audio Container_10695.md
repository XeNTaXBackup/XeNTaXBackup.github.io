## Post #1
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-08-16T02:02:11+00:00
- Post Title: Rayman Legends PC Audio Container

The audio in Rayman Legends on PC uses a PCM & ADPCM container unknown to me. No RIFF header for either however playing the PCM files raw works with clipping in the intro. (Obviously the header) ADPCM though doesn't work even creating a Microsoft ADPCM GENH file.

PCM:


ADPCM:
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-08-19T08:01:32+00:00
- Post Title: Rayman Legends PC Audio Container

Have you tried all XORs? You can find the script in my big topic. Cut the header first of course. If you have found out the XOR, just use the same script to process the whole file (explanation inside).
## Post #3
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-08-20T12:34:06+00:00
- Post Title: Rayman Legends PC Audio Container

> Reply from AlphaTwentyThree
>
> Have you tried all XORs? You can find the script in my big topic. Cut the header first of course. If you have found out the XOR, just use the same script to process the whole file (explanation inside).

I'm not sure I understand, I've tried the script though I don't think it'll be useful in my hands. I have no idea what to do with it.

[RLpcm&adpcm.rar](https://app.box.com/s/8qgslvn2m8o2epjgq2sh)

Here's a quick rar with 2 audio files, one pcm and adpcm if anyone wants to try their hand.
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-08-20T16:38:25+00:00
- Post Title: Rayman Legends PC Audio Container

No XOR needed, PCM files are ok.
Need more ADPCM samples.
## Post #5
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-08-20T23:32:13+00:00
- Post Title: Rayman Legends PC Audio Container

> Reply from AlphaTwentyThree
>
> No XOR needed, PCM files are ok.
Need more ADPCM samples.

Here's 5 more ADPCM samples

[RL5adpcm](https://app.box.com/s/081l90kn9y1j2do14qj5)
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-08-25T13:26:39+00:00
- Post Title: Rayman Legends PC Audio Container

Ok, found the time to write the script. Had to implement the generic header first.
Try if this works:

```
# (c) 2013-08-30 by AlphaTwentyThree of XeNTaX
# script for QuickBMS http://quickbms.aluigi.org

get DUMMY long
idstring "RAKI"
goto 0x10
getDstring TYPE 4
get OFFSET long
FindLoc GO string "data" 0 ""
math GO += 8
goto GO
get SIZE long
get CODEC short
get CH short
get FREQ long

set NAME ""
if TYPE == "pcm "
	set BLOCKALIGN 4
	set BITS 16
	callfunction PCM 1
elif TYPE == "adpc"
	set BITS 4
	set INTERLEAVE 0x8c
	set CODEC 0xb
	callfunction GENH 1
endif


startfunction PCM
	endian little
	set PRE SIZE
	math PRE += 0x2c
	putVarChr MEMORY_FILE PRE 0
	log MEMORY_FILE 0 0
	set MEMORY_FILE binary "\x52\x49\x46\x46\x20\xC0\xB1\x00\x57\x41\x56\x45\x66\x6D\x74\x20\x10\x00\x00\x00\x01\x00\x02\x00\x44\xAC\x00\x00\x10\xB1\x02\x00\x04\x00\x10\x00\x64\x61\x74\x61\xFC\xBF\xB1\x00"
	append
	log MEMORY_FILE OFFSET SIZE
	append
	set RIFFSIZE SIZE
	math RIFFSIZE += 36
	set AVGBYTES FREQ
	if CODEC != 2
		math AVGBYTES *= BLOCKALIGN
	endif
	
	putvarchr MEMORY_FILE 0x04 RIFFSIZE long
	putvarchr MEMORY_FILE 0x14 CODEC short          # wFormatTag: Microsoft PCM Format (0x0001)
	putvarchr MEMORY_FILE 0x16 CH short   # wChannels
	putvarchr MEMORY_FILE 0x18 FREQ short   # dwSamplesPerSec
	putvarchr MEMORY_FILE 0x1c AVGBYTES long    # dwAvgBytesPerSec
	putvarchr MEMORY_FILE 0x20 BLOCKALIGN short # wBlockAlign
	putvarchr MEMORY_FILE 0x22 BITS short       # wBitsPerSample
	putvarchr MEMORY_FILE 0x28 SIZE long
	if NAME == ""
		get NAME basename
		string NAME += ".wav"
	endif
	get SIZE asize MEMORY_FILE
	log NAME 0 SIZE MEMORY_FILE
endfunction

startfunction GENH
	get FSIZE asize
	math FSIZE += 0x1000
	putVarChr MEMORY_FILE FSIZE 0
	log MEMORY_FILE 0 0
	putVarChr MEMORY_FILE 0 0x484e4547 long
	putVarChr MEMORY_FILE 0x4 CH long
	putVarChr MEMORY_FILE 0x8 INTERLEAVE long
	putVarChr MEMORY_FILE 0xc FREQ long
	putVarChr MEMORY_FILE 0x10 0xffffffff long
	set SAMPLES SIZE
	math SAMPLES *= 8
	math SAMPLES /= BITS
	putVarChr MEMORY_FILE 0x14 SAMPLES long
	putVarChr MEMORY_FILE 0x18 CODEC long
	math OFFSET += 0x1000
	putVarChr MEMORY_FILE 0x1c OFFSET long
	putVarChr MEMORY_FILE 0x20 0x1000 long
	putVarChr MEMORY_FILE 0x300 FSIZE long
	putVarChr MEMORY_FILE 0x304 0x32304756 long
	putVarChr MEMORY_FILE 0xfff 0 byte
	math FSIZE -= 0x1000
	append
	log MEMORY_FILE 0 FSIZE
	append
	get NAME filename
	string NAME += ".genh"
	get SIZE asize MEMORY_FILE
	log NAME 0 SIZE MEMORY_FILE
endfunction
```
## Post #7
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-08-30T13:05:08+00:00
- Post Title: Rayman Legends PC Audio Container

> Reply from AlphaTwentyThree
>
> Ok, found the time to write the script. Had to implement the generic header first.
Try if this works:
Code: Select allscript

I've tried the script and a few PCM files with different headers wont work with it and only outputs the header made by the script. I've also included a adpcm file that distorts after the audio track plays.

EDIT: Added an unworking adpcm CPK.

[https://app.box.com/s/wf5ye8p3g92ryiyp8kxl](https://app.box.com/s/wf5ye8p3g92ryiyp8kxl)
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-08-30T20:41:11+00:00
- Post Title: Rayman Legends PC Audio Container

Corrected the script for PCM files, also corrected the sample calculation for the GENH header and some variable offsets.

However:
The problem with the ADPCM file is that it's MS ADPCM mono, which isn't supported by GENH nor vgmstream. I'm quite at a loss here... If anyone can help I'd be thankful!
## Post #9
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-08-30T21:19:33+00:00
- Post Title: Rayman Legends PC Audio Container

> Reply from AlphaTwentyThree
>
> Corrected the script for PCM files, also corrected the sample calculation for the GENH header and some variable offsets.

However:
The problem with the ADPCM file is that it's MS ADPCM mono, which isn't supported by GENH nor vgmstream. I'm quite at a loss here... If anyone can help I'd be thankful!

Thanks for the quick update, Alpha23. Is it possible for the single channel be copied as the second channel and then made as a pseudo 2ch mono ADPCM GENH temporarily until single channel GENH is supported?
## Post #10
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-08-31T09:23:10+00:00
- Post Title: Rayman Legends PC Audio Container

I'll ask snakemeat first.
Apart from that: I'm not even sure if ms_adpcm even supports mono. And I'm not sure if it's possible to create pseudo-stereo files, but we'll see.
## Post #11
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-09-02T21:01:14+00:00
- Post Title: Rayman Legends PC Audio Container

> Reply from AlphaTwentyThree
>
> I'll ask snakemeat first.
Apart from that: I'm not even sure if ms_adpcm even supports mono. And I'm not sure if it's possible to create pseudo-stereo files, but we'll see.

Alpha23 do you have to use GENH headers on the ADPCM files because they are actually Microsoft WAV ADPCM files which if headers were applied, could solve the mono issue.
## Post #12
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-09-02T22:02:22+00:00
- Post Title: Rayman Legends PC Audio Container

> Reply from !!!!!
>
> AlphaTwentyThree wrote:I'll ask snakemeat first.
Apart from that: I'm not even sure if ms_adpcm even supports mono. And I'm not sure if it's possible to create pseudo-stereo files, but we'll see.

Alpha23 do you have to use GENH headers on the ADPCM files because they are actually Microsoft WAV ADPCM files which if headers were applied, could solve the mono issue.
Well, if somebody could tell me how to construct a valid msadpcm header...
## Post #13
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2013-09-04T21:48:42+00:00
- Post Title: Rayman Legends PC Audio Container

Is possible make a reverse way? convert wav to wav.cpk?
## Post #14
- Username: lonrot
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 02, 2015 1:38 pm
- Post datetime: 2015-09-02T05:49:29+00:00
- Post Title: Rayman Legends PC Audio Container

AlphaTwentyThree please update the script to include sound effects as well!

I managed to extract most music, however with smaller sound effects the conversion returns this useless "filename.wav.ckd.genh" format, and renaming it does nothing.

Here are some original wav.ckd files that are not converting properly:
[https://dl.dropboxusercontent.com/u/621 ... ds-sfx.zip](https://dl.dropboxusercontent.com/u/62131673/MISC/rayman-legends-sfx.zip)

Thank you!
## Post #15
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-09-02T09:26:09+00:00
- Post Title: Rayman Legends PC Audio Container

As I said, I don't know how to construct a working MSADPCM mono header. The genh header is correct but for some reason vgmstream doesn't play the files.
As of now there's nothing I can do to solve the problem I'm afraid.
## Post #16
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-09-02T13:46:03+00:00
- Post Title: Re: Rayman Legends PC Audio Container

for mono (should work for stereo as well) adpcm files that lonrot posted before

```
goto 0x38
get DATA_SIZE long
set RIFF_SIZE long DATA_SIZE
math RIFF_SIZE += 0x46
set FULL_SIZE long RIFF_SIZE
math FULL_SIZE += 0x8
get CODEC short
get CHANNELS short
get FREQ long
get BPS long
get ALIGN short
get UNKNOWN1 long
get UNKNOWN2 long
get UNKNOWN3 long
get UNKNOWN4 long
get UNKNOWN5 long
get UNKNOWN6 long
get UNKNOWN7 long
get UNKNOWN8 long
get UNKNOWN9 long
set RIFF long 0x46464952
set WAVE long 0x45564157
set FMT long 0x20746d66
set FMT_SIZE long 0x00000032
set DATA long 0x61746164
putVarChr MEMORY_FILE FULL_SIZE 0
log MEMORY_FILE 0 0
append
putVarChr MEMORY_FILE 0x0 RIFF long
putVarChr MEMORY_FILE 0x4 RIFF_SIZE long
putVarChr MEMORY_FILE 0x8 WAVE long
putVarChr MEMORY_FILE 0xC FMT long
putVarChr MEMORY_FILE 0x10 FMT_SIZE long
putVarChr MEMORY_FILE 0x14 CODEC short
putVarChr MEMORY_FILE 0x16 CHANNELS short
putVarChr MEMORY_FILE 0x18 FREQ long
putVarChr MEMORY_FILE 0x1C BPS long
putVarChr MEMORY_FILE 0x20 ALIGN short
putVarChr MEMORY_FILE 0x22 UNKNOWN1 long
putVarChr MEMORY_FILE 0x26 UNKNOWN2 long
putVarChr MEMORY_FILE 0x2A UNKNOWN3 long
putVarChr MEMORY_FILE 0x2E UNKNOWN4 long
putVarChr MEMORY_FILE 0x32 UNKNOWN5 long
putVarChr MEMORY_FILE 0x36 UNKNOWN6 long
putVarChr MEMORY_FILE 0x3A UNKNOWN7 long
putVarChr MEMORY_FILE 0x3E UNKNOWN8 long
putVarChr MEMORY_FILE 0x42 UNKNOWN9 long
putVarChr MEMORY_FILE 0x46 DATA long
putVarChr MEMORY_FILE 0x4A DATA_SIZE long
log MEMORY_FILE 0x6E DATA_SIZE
log NAME 0 FULL_SIZE MEMORY_FILE
```
## Post #17
- Username: lonrot
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 02, 2015 1:38 pm
- Post datetime: 2015-09-02T22:33:03+00:00
- Post Title: Re: Rayman Legends PC Audio Container

@AlphaTwentyThree That's a bummer! Thanks for taking the time to respond 

Update:
@spider91 Thanks, I will try it right away.
## Post #18
- Username: lonrot
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 02, 2015 1:38 pm
- Post datetime: 2015-09-03T00:29:26+00:00
- Post Title: Re: Rayman Legends PC Audio Container

@spider

The script fails to convert sfx_buzzsaw_move_brass_02.wav when processing the file list provided in the previous link.

```
       Can't read 15631996 bytes from offset 00017a32.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0    99%   96762      96818

Last script line before the error or that produced the error:
  51  log MEMORY_FILE 0x6E DATA_SIZE

Press RETURN to quit
```
## Post #19
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-09-03T00:38:04+00:00
- Post Title: Re: Rayman Legends PC Audio Container

Upload a file that gives that error. I've tested it on all files from your previous acrhieve only and it worked well.
## Post #20
- Username: lonrot
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 02, 2015 1:38 pm
- Post datetime: 2015-09-03T00:43:01+00:00
- Post Title: Re: Rayman Legends PC Audio Container

> Reply from spider91
>
> Upload a file that gives that error. I've tested it on all files from your previous acrhieve only and it worked well.
[Here's the file.](https://dl.dropboxusercontent.com/u/62131673/MISC/sfx_buzzsaw_impact_02.wav.zip)
## Post #21
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-09-03T00:47:56+00:00
- Post Title: Re: Rayman Legends PC Audio Container

Maybe it's about version of quickbms. What is your version?
## Post #22
- Username: lonrot
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 02, 2015 1:38 pm
- Post datetime: 2015-09-03T00:48:56+00:00
- Post Title: Re: Rayman Legends PC Audio Container

It seems that the script is failing only when doing batch requests with folders and subfolders.

When selecting a folder, and selecting "*".

It crashes immediately with the first file.

```
       Can't read 335517175 bytes from offset 00006a77.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0    99%   27199      27255

Last script line before the error or that produced the error:
  51  log MEMORY_FILE 0x6E DATA_SIZE

Press RETURN to quit

```
## Post #23
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-09-03T00:56:19+00:00
- Post Title: Re: Rayman Legends PC Audio Container

You can create batch file like this (just change pathes to ones you are using)

```
cd "%%~dpi"
"C:\Users\spider91\Desktop\test\quickbms.exe" "C:\Users\spider91\Desktop\test\script.txt" "%%i"
)
pause

```
## Post #24
- Username: lonrot
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 02, 2015 1:38 pm
- Post datetime: 2015-09-03T01:14:26+00:00
- Post Title: Re: Rayman Legends PC Audio Container

> Reply from spider91
>
> You can create batch file like this (just change pathes to ones you are using)
Code: Select allfor /r %%i in (*.ckd) do (
cd "%%~dpi"
"C:\Users\spider91\Desktop\test\quickbms.exe" "C:\Users\spider91\Desktop\test\script.txt" "%%i"
)
pause

Some questions:

1) What format/extension is the batch file?

2) Where should the batch file be placed at?

3) Is the script.txt the same as script.bms?

4) In the batch file, What calls the location of the root folder (where the files are present)?

Thank you.
## Post #25
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-09-03T01:35:01+00:00
- Post Title: Re: Rayman Legends PC Audio Container

1) It's a simple .txt file renamed to .bat
2) In folder with .ckd files or in the main game folder (it will scan subdirectories too)
3) Yes, it's the same script i posted before.
4) Can't undestand this one.
## Post #26
- Username: lonrot
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 02, 2015 1:38 pm
- Post datetime: 2015-09-03T01:38:49+00:00
- Post Title: Re: Rayman Legends PC Audio Container

Following [this guide](http://forum.xentax.com/viewtopic.php?f=13&t=4450), I made the following batch.bat file:

```
for %%i in (*.ckd) DO %CD%\quickbms.exe -o script.bms "%%i" "%CD%" 
```


Everything is in a single folder, quickbms.exe, script.bms and every existing wav.cpk file, no subfolders.

The batch file returns:


Not a single file is saved. What am I doing wrong?

Update: Renamed "Rayman Legends" to RaymanLegends and now it works!
## Post #27
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-09-03T01:41:08+00:00
- Post Title: Re: Rayman Legends PC Audio Container

Replace

```
%CD%\quickbms.exe
```

with

```
"%CD%\quickbms.exe"
```


You must do it when you have spaces in your filenames/pathes.
## Post #28
- Username: lonrot
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 02, 2015 1:38 pm
- Post datetime: 2015-09-03T01:44:10+00:00
- Post Title: Re: Rayman Legends PC Audio Container

Thanks spider, "Rayman Legends" was causing the error.
