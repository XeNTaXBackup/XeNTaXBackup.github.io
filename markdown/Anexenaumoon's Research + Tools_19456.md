## Post #1
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-02-05T21:00:30+00:00
- Post Title: Anexenaumoon's Research + Tools

Figured this would be the best place for this... I will be documenting some games I research over sometime (Mainly PS2 games, because the site I belong to does not have enough PS2 rips). So, enjoy, hopefully these will become of use....

To start:

This QuickBMS script extracts PS-ADPCM samples from Ice Age 2: The Meltdown's *.SFX banks. The music ones are playable in vgmstream, but the samples require a header. Here's the script:

```
#Extracts Raw PS-ADPCM Samples
#SFX files prefixed with "mus" can be re-named and played properly as MUSX in vgmstream.
idstring "MUSX"
get NULL short
get ID short

if ID == 0x2d50
	goto 0
	callfunction VERONE
elif ID == 0x2d40
	goto 0
	callfunction VERTWO
else
	print "Invalid ID."
endif 

startfunction VERONE
	idstring "MUSX"
	get BASENAME basename	
	get FLAGS long
	get VER long
	get ARKSIZE long
	idstring "PS2_"
	get NULL long
	get NULL long
	get ZERO long
	get TB long
	get TBS long
	get INFO_OFF long
	get INFO_SIZE long
	getdstring SKIP 0x8
	get BASE_OFF long
	get BASE_SIZE long
	goto INFO_OFF
	get FCOUNT long
	for i = 0 < FCOUNT
		get NULL long
		get OFFSET long
		math OFFSET + BASE_OFF
		get SIZE long
		get SAMPLERATE long
		getdstring SKIP 0x10
		set NAME string BASENAME
		string NAME += "_"
		string NAME += i
		string NAME += ".iam"
		log MEMORY_FILE 0 0
		putvarchr MEMORY_FILE 0 SAMPLERATE long
		append
		log MEMORY_FILE OFFSET SIZE
		math SIZE + 4
		append
		log NAME 0 SIZE MEMORY_FILE
	next i 
endfunction

startfunction VERTWO
	idstring "MUSX"
	get FLAGS long
	get ID long
	get NULL long
	idstring "PS2_"
	get NULL long
	get NULL long
	get ZERO long
	get OFFTABLE long
	get OFFSIZE long
	get BASE_OFF long
	xmath FCOUNT "OFFSIZE / 4"
	goto OFFTABLE
	for i = 0 < FCOUNT
		get OFFSET long
		set CHECK long FCOUNT
		math CHECK - 1
		if i == CHECK
			math OFFSET + BASE_OFF	
			get ENDSIZE asize
			xmath SIZE "ENDSIZE - OFFSET"
		else
			get OFFTWO long
			math OFFTWO + BASE_OFF
			math OFFSET + BASE_OFF
			xmath SIZE "OFFTWO - OFFSET"
		endif
		goto -4 0 SEEK_CUR
		get BASENAME basename
		set NAME string BASENAME
		string NAME += "_"
		string NAME += i
		string NAME += ".iam"
		log NAME OFFSET SIZE
	next i 
endfunction

```


Just generate a vgmstream txth after the *.iam's are extracted. (The sample rate is put at 0x0 for ease as different files use sample sizes. Note: Version 2's txth will be different.)
