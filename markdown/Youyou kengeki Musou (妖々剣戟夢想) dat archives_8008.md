## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-08T06:22:50+00:00
- Post Title: Youyou kengeki Musou (妖々剣戟夢想) dat archives

For those that have the game. Model thread [viewtopic.php?f=16&t=6958](http://forum.xentax.com/viewtopic.php?f=16&t=6958)
I wrote the script for the pack001.dat (just BGM) and also the rpack_##.dat (rest of the resources)

Observe my rough file-checking because I didn't know how to XOR each character of a string with 0xA4.

note: for the music archive, there's actually more stuff after the given size (like maybe a couple hundred bytes). I don't know the OGG format so I'm not sure if those are actually part of the file itself. The file doesn't play if I take those as well though, so maybe it's just stuff for the game...

```

startfunction rpack
	
	get null byte
	get unk long
	get tableStart long
	get FILES long
	goto tableStart
	for i = 0 < FILES do
		filexor 0xA4
		get len long
		getdstring NAME len
		get null byte
		get OFFSET long
		get unk2 long
		get SIZE long
		get unk3 long
		
		putarray 0 i NAME
		putarray 1 i OFFSET
		putarray 2 i SIZE
		
	next i
	savepos START

	for i = 0 < FILES do
		getarray NAME 0 i
		getarray OFFSET 1 i
		getarray SIZE 2 i
		
		math OFFSET += START
		filexor 0x00
		log NAME OFFSET SIZE
	next i
endfunction

startfunction normal
	get null byte
	get FILES long
	get unk LONG
	goto 0x20
	for i = 0 < FILES do
		get OFFSET long
		get null long
		get SIZE long
		get null long
		get NUM long
		get unk long
		get null long
		get null long		
		set name = i
		string name += ".ogg"
		log name OFFSET SIZE
	next i
endfunction
	

getdstring idstring 7
if idstring == "thsndpk" then
	callfunction normal
else
	goto 0
	filexor 0xA4
	getdstring idstring 7
	if idstring == "mgbpack" then
		callfunction rpack
	end if
end if
```
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-01-08T06:50:06+00:00
- Post Title: Youyou kengeki Musou (妖々剣戟夢想) dat archives

all you do is this
filexor "0x4A"
get string
filexor ""
that turns it on just while you read the string.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-08T07:26:35+00:00
- Post Title: Youyou kengeki Musou (妖々剣戟夢想) dat archives

One archive has unencrypted file header while the other archives are encrypted, so I want to read 7 bytes first, check if it's the unencrytped string, then XOR it.
