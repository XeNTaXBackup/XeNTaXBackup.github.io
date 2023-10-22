## Post #1
- Username: DekodaLiyon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 06, 2022 10:03 pm
- Post datetime: 2022-08-06T14:15:31+00:00
- Post Title: Wipeout Fusion (PS2) - IPS files

Hi everyone!

So, I've been looking over the internet for a while now and I cant seem to find an answer to this problem.

I've decided to rip Wipeout Fusion on the PS2, and I found that the video files seem to be in a strange container format called .IPS. I believe this was discussed here about 13 years ago, but the thread died quickly ([viewtopic.php?f=21&t=3054&p=31844&hilit=.ips#p31844](https://forum.xentax.com/viewtopic.php?f=21&t=3054&p=31844&hilit=.ips#p31844)). 

I would like to ask if there has been any success in trying to decompile this format into playable video? Google searches and research leaves very little results. I do know that the format is IPU video interleaved with ADPCM audio, and was used alot in Atlus SMT games. Other than that, nothing else. 

Please if you can advise how this can decompiled?
## Post #2
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2022-08-19T03:00:34+00:00
- Post Title: Wipeout Fusion (PS2) - IPS files

Honestly, this thread is more suited in "Video file formats" section, but anyway....

Wipeout Fusion's IPS apparently is different from SMT:Nocturne's IPS. There's also an IPF file (basically the same as IPS but lacks the audio stream) which used in the game's menu as a background.
I wrote a BMS script to demux those IPS files to IPU+WAV combo (or just IPU for the IPF). Inside the script also included workaround switches for few files (Fix videos not playing/stays at frame 0 for WOF.IPS/WOFAC3.IPS and also to extract the audio stream as Dolby AC3 instead of WAV for WOFAC3.IPS. Just change the 0 to 1 to activate the switch)

Here's the script:

```
# For use with QuickBMS (http://aluigi.altervista.org/quickbms.htm)

math FREEZE_FRAME_WORKAROUND = 0 # For both WOF.IPS and WOFAC3.IPS
math EXTRACT_AC3             = 0 # For WOFAC3.IPS only

get IPS_SZ asize
get FNAME basename

# WAV parameters for the audio
math FREQ       = 48000 # Sample rate
math CHAN       = 2     # Audio channels
math BPS        = 16    # Bits per second

log MEMORY_FILE  0 0
log MEMORY_FILE2 0 0
log MEMORY_FILE3 0 0
log MEMORY_FILE4 0 0

string VNAME p "%s.ipu" FNAME
if EXTRACT_AC3 == 1
	string ANAME p "%s.ac3" FNAME
else
	string ANAME p "%s.wav" FNAME
endif

IDString "IPU"
getdstring TYPE 1
get WIDTH long
get HEIGHT long
get FRAMES long
get CHUNK_SZ long

append

putdstring "ipum" 4 MEMORY_FILE

if EXTRACT_AC3 == 0
	if TYPE == "S"
		putdstring "RIFF" 4 MEMORY_FILE2
	endif
endif

do
	savepos CURRPOS
	string STAT p "Processing chunk offset 0x%08x" CURRPOS
	print %STAT%
	get VID_SZ long
	if TYPE == "S"
		get AUD_SZ long
	endif
	set CURRPOS_TMP CURRPOS
	math CURRPOS_TMP + 0x40
	if FREEZE_FRAME_WORKAROUND == 1
		set VID_SZ_TMP VID_SZ
		math VID_SZ_TMP - 4
		log MEMORY_FILE3 CURRPOS_TMP VID_SZ_TMP
	else
		log MEMORY_FILE3 CURRPOS_TMP VID_SZ
	endif
	
	if TYPE == "S"
		math CURRPOS_TMP + VID_SZ
		log MEMORY_FILE4 CURRPOS_TMP AUD_SZ
	endif
	math CURRPOS + CHUNK_SZ
	goto CURRPOS
while CURRPOS < IPS_SZ

get IPU_DATA_SZ asize MEMORY_FILE3
math IPU_DATA_SZ + 0x08
put IPU_DATA_SZ long MEMORY_FILE
put WIDTH short MEMORY_FILE
put HEIGHT short MEMORY_FILE
put FRAMES long MEMORY_FILE
math IPU_DATA_SZ - 0x08
log MEMORY_FILE 0 IPU_DATA_SZ MEMORY_FILE3

if EXTRACT_AC3 == 0
	if TYPE == "S"
		get PCM_DATA_SZ asize MEMORY_FILE4
		xmath WAV_SZ_TMP "PCM_DATA_SZ + 0x24"
		put WAV_SZ_TMP long MEMORY_FILE2
		putdstring "WAVE" 4 MEMORY_FILE2
		
		putdstring "fmt " 4 MEMORY_FILE2
		put 0x10 long MEMORY_FILE2
		put 0x01 short MEMORY_FILE2
		put CHAN short MEMORY_FILE2
		put FREQ long MEMORY_FILE2
		xmath BYTE_RATE "FREQ * CHAN * BPS / 8"
		put BYTE_RATE long MEMORY_FILE2
		xmath BLOCK_ALIGN "CHAN * BPS / 8"
		put BLOCK_ALIGN short MEMORY_FILE2
		put BPS short MEMORY_FILE2
		
		putdstring "data" 4 MEMORY_FILE2
		put PCM_DATA_SZ long MEMORY_FILE2
		log MEMORY_FILE2 0 PCM_DATA_SZ MEMORY_FILE4
	endif
endif

append

get IPU_SZ asize MEMORY_FILE
log VNAME 0 IPU_SZ MEMORY_FILE

if TYPE == "S"
	if EXTRACT_AC3 == 0
		get WAV_SZ asize MEMORY_FILE2
		log ANAME 0 WAV_SZ MEMORY_FILE2
	else
		get AUD_SZ asize MEMORY_FILE4
		log ANAME 0 AUD_SZ MEMORY_FILE4
	endif
endif

```


Then, just convert the IPU to M2V or mux then convert both of the IPU and WAV directly to your format of choice by using FFMPEG (It supports IPU video since version 4.4), though you might need to add "fps" and "setpts" video filters to correct the video framerates, since FFMPEG assumes the IPU video has a framerate of 25 fps instead of 29.97. Or you can use the IPUDecoder, then mux/convert both of the m2v and wav later with FFMPEG.
## Post #3
- Username: samucapimenta55
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 20, 2022 6:15 am
- Post datetime: 2022-09-09T19:21:04+00:00
- Post Title: Wipeout Fusion (PS2) - IPS files

Friend how to open edit and watch a PS2 game video *.IPU file?
