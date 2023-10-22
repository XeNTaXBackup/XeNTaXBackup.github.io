## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-07-22T10:05:24+00:00
- Post Title: Playstation ADPCM - problem with Quake II files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-07-22T13:39:52+00:00
- Post Title: Playstation ADPCM - problem with Quake II files

Sorry for posting a bit rashly, just found out how to deal with XIA files. They are actually interleaved XA files (XAI - should have thought a bit about that letter  ), that's why they respond so strangely to cutting. The crucial offsets of each 0x930-byte are 0x11 (byte) and 0x12 (short). 0x11 holds the layer number (e.g. which blocks belong together), 0x12 the contained data. When the latter equals 0x164, the block is processed, when it's zero, the procedure is quit and continued with the next layer.
The following script deinterleaves the XA streams out of any Playstation XAI file, cuts it at the right spot and adds a PSX ADPCM header. All extracted files are playable with vgmstream.  The script looks a bit nasty because I needed a workaround with a QUIT marker. Have fun. 

```
set INTERL 0x930
callfunction getlayers 1
set JUMP INTERL
math JUMP *= LAYERS
get FSIZE asize
for i = 1 <= LAYERS
	log MEMORY_FILE 0 0
	set MEMORY_FILE binary "\x52\x49\x46\x46\xe4\x04\xbe\x02\x43\x44\x58\x41\x66\x6d\x74\x20\x10\x0\x0\x0\x0\x0\x0\x0\x1\x55\x58\x41\x1\x0\x0\x0\x0\x0\x0\x0\x64\x61\x74\x61\xc0\x4\xbe\x2"
	set OFFSET i
	math OFFSET -= 1
	math OFFSET *= INTERL
	math OFFSET += HEADER
	set QUIT 0
	append
	for
		set CHECK OFFSET
		math CHECK += 0x12
		goto CHECK
		get DAT short # audio marker
		if DAT == 0
			set QUIT 1
		endif
		set TEST OFFSET
		math TEST += INTERL
		if TEST == FSIZE
			set QUIT 2
		endif
		if QUIT == 0
			log MEMORY_FILE OFFSET INTERL
			math OFFSET += JUMP
		elseif QUIT == 2
			log MEMORY_FILE OFFSET INTERL
			break
		else
			break
		endif
	next
	append
	get SIZE asize MEMORY_FILE
	set RIFFSIZE SIZE
	math RIFFSIZE -= 8
	set DSIZE SIZE
	math DSIZE -= 0x2c
	putVarChr MEMORY_FILE 0x04 RIFFSIZE long
	putVarChr MEMORY_FILE 0x28 DSIZE long
	get NAME basename
	string NAME += "_"
	string NAME += i
	string NAME += ".xa"
	log NAME 0 SIZE MEMORY_FILE
next i

startfunction getlayers
	set LAYER 0x941
	set LAYERS 0
	DO
		math LAYERS += 1
		goto LAYER
		get L byte
		math LAYER += 0x930
	WHILE L != 0
endfunction

```
