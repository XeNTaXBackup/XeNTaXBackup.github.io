## Post #1
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-01T14:15:29+00:00
- Post Title: Deep Black Reloaded [.bsrt files]

Global.pack contains .bsrt files, which contain some of the texts of the game. Is there a way to edit them?
I've attached one of the .bsrt files.
[00.7z](https://xentaxbackup.github.io/file/5246_00.7z)
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-01T17:28:29+00:00
- Post Title: Deep Black Reloaded [.bsrt files]

I've taken a look at the file. Has a strange structure with some kind of referrers. Tried to extract the contents but something's wrong with the offsets and sizes. 
If anyone wants to take a look at what I've done:

```
get FILES1 long # names
get UNK long
get FILES2 long # referrers
get INFOOFF long # sizes/offsets
set NAMEOFF 0x1c
set DATA FILES2
math DATA *= 0xc
math DATA += INFOOFF
set i 0
goto INFOOFF
for k = 1 <= FILES2
	get FILE long
	get UNK long
	get OFFSET long
	if FILE == 0
		append
		log MEMORY_FILE NAMEOFF 0x40
		append
		math NAMEOFF += 0x48
		math OFFSET += DATA
		set WRITEPOS i
		math WRITEPOS *= 4
		putVarChr MEMORY_FILE2 WRITEPOS OFFSET long
		math i += 1
	endif
next k
# get SIZE asize MEMORY_FILE
# log "NAMES_MEM" 0 SIZE MEMORY_FILE
# get SIZE asize MEMORY_FILE2
# log "OFFSETS_MEM" 0 SIZE MEMORY_FILE2
set NAMEOFF 0
goto 0 MEMORY_FILE2
for i = 1 <= FILES1
	get OFFSET long MEMORY_FILE2
	savepos MYOFF MEMORY_FILE2
	if i != FILES1
		get SIZE long MEMORY_FILE2
	else
		get SIZE asize
	endif
	math SIZE -= OFFSET
	goto NAMEOFF MEMORY_FILE
	getDstring NAME 0x40 MEMORY_FILE
	string NAME += ".txt"
	savepos NAMEOFF MEMORY_FILE
	log NAME OFFSET SIZE
	goto MYOFF MEMORY_FILE2
next i
```
