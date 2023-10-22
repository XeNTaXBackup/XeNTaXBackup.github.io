## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-01T16:46:11+00:00
- Post Title: XMA cue markers

Hi there!
I've just encountered some XMA files with cue markers. I've exported them and converted the XMA file to wav but now I'm facing the problem that the marker positions need to be transformed to the correct ones in the wave file. I thought that these are just the sample counts so there wouldn't be any need to adjust them, but apparently not.
Can anyone possibly take a look at this example? Thanks a lot.
sample: [http://www.sendspace.com/file/k3fe8b](http://www.sendspace.com/file/k3fe8b)
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-04-01T23:26:55+00:00
- Post Title: XMA cue markers

It's possible that they don't account for the encoder latency, which is I think 128 samples (been a while, could be wrong).
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-03T15:59:15+00:00
- Post Title: XMA cue markers

Ok, I've double-ckecked the structures of standard wave cue markers and XMA cue markers. There are just two differences:
- xma markers are normally big endian
- wave cue markers have additional "ltxt" sections per marker. 
The latter means that XMA markers seem to alwasys have the same start and end point.
I'm currently writing a script that converts XMA markers to standard wave markers. I'll post it when it's finished.
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-03T18:59:31+00:00
- Post Title: XMA cue markers

Wow, what a hazzle! I know I could have made it differently but the script works so far. 
The script first reads all available information about the markers (ID, start sample and label - if available), adds the needed ltxt sections per marker and composes the new cue file from scratch. I'll update my cue adder soon, but for now you can just copy the cue section to the end of the wave file and adjust the riff size at 0x4.

```
# 
# (c) 2012-04-03 by AlphaTwentyThree of XeNTaX

include "func_writename.bms"
endian big
idstring "cue "
get CUESIZE long
if CUESIZE >= 0x100000 # work-around
	endian little
endif
get MARKERS long
for i = 1 <= MARKERS
	get MID long # marker ID
	get MSAMP1 long # always same as MSAMP2 (?)
	idstring "data"
	get ZERO long
	get ZERO long
	get MSAMP2 long
	putArray 0 MID MSAMP1 long
	putArray 1 MID MSAMP2 long
	putArray 2 MID "" string # reset
next i
idstring "LIST"
get LISTSIZE long
if LISTSIZE == 0 # lables are optional
	callfunction wavcue 1
	cleanexit
endif
idstring "adtl" # table, empty in XMA markers
get CSIZE asize
math CSIZE -= 1 # last byte is 0
do
	get IDENT long
	if IDENT == 0x6c6162
		savepos MYOFF
		math MYOFF += 1
		goto MYOFF
	endif
	get LSIZE long
	get MID long
	set MNAMEL LSIZE
	math MNAMEL -= 4
	getDstring MNAME MNAMEL
	putArray 2 MID MNAME string
	savepos TEST
while TEST < CSIZE
callfunction wavcue 1

startfunction wavcue
	endian little
	putVarChr MEMORY_FILE 0 0x20657563 long # "cue "
	set CUESIZE MARKERS
	math CUESIZE *= 0x18
	math CUESIZE += 4
	putVarChr MEMORY_FILE 4 CUESIZE long
	putVarChr MEMORY_FILE 8 MARKERS long
	set WPOS CUESIZE
	math WPOS += 8
	putVarChr MEMORY_FILE WPOS 0x5453494c long # "LIST"
	math WPOS += 4
	set LISTSZ WPOS # position of LIST size
	math WPOS += 4
	putVarChr MEMORY_FILE WPOS 0x6c746461 long # "adtl"
	math WPOS += 4
	set LTXTPOS WPOS
	set WPOS 0xc
	for i = 1 <= MARKERS # "cue " section
		putVarChr MEMORY_FILE WPOS i long # MID
		math WPOS += 4
		getArray MSAMP1 0 i
		putVarChr MEMORY_FILE WPOS MSAMP1 long
		math WPOS += 4
		putVarChr MEMORY_FILE WPOS 0x61746164 long # "data"
		math WPOS += 0xc
		getArray MSAMP2 1 i
		putVarChr MEMORY_FILE WPOS MSAMP2 long
		math WPOS += 4
		set NXT i
		math NXT -= 1
		math NXT *= 0x1c
		math NXT += LTXTPOS
		putVarChr MEMORY_FILE NXT 0x7478746c long # "ltxt"
		math NXT += 4
		putVarChr MEMORY_FILE NXT 0x14 long
		math NXT += 4
		putVarChr MEMORY_FILE NXT i long
		math NXT += 8
		putVarChr MEMORY_FILE NXT 0x206e6772 long # "rgn "
	next i
	set WPOS NXT
	math WPOS += 0xc
	for i = 1 <= MARKERS
		getArray LABEL 2 i
		if LABEL != ""
			putVarChr MEMORY_FILE WPOS 0x6c62616c long # "labl"
			math WPOS += 4
			strlen LABSIZE LABEL
			math LABSIZE += 5
			putVarChr MEMORY_FILE WPOS LABSIZE long
			math WPOS += 4
			putVarChr MEMORY_FILE WPOS i long # MID
			math WPOS += 4
			set STRPOS WPOS
			set NAME LABEL
			callfunction writename 1
			get WPOS asize MEMORY_FILE
			putVarChr MEMORY_FILE WPOS 0 byte
			math WPOS += 1
		endif
	next i
	get SIZE asize MEMORY_FILE
	set PUTLSIZE SIZE
	math PUTLSIZE -= LISTSZ
	math PUTLSIZE -= 4
	putVarChr MEMORY_FILE LISTSZ PUTLSIZE long
	get NAME basename
	string NAME += ".wcue"
	log NAME 0 SIZE MEMORY_FILE
endfunction
```
