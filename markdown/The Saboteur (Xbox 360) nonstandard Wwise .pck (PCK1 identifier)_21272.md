## Post #1
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2019-10-20T17:49:43+00:00
- Post Title: The Saboteur (Xbox 360) nonstandard Wwise *.pck ("PCK1" identifier)

Good day everyone, I'd highly appreciate any help with extracting banks & audio streams from [this (cuts from start and end of a *.pck file)](https://drive.google.com/open?id=1-hrD32iGsptZKPmGuBAVbWIh6vii3UC-): it's probably a slight mutation of normal Wwise *.pck ("AKPK" identifier) but right now it makes it incompatible with scripts that usually work with such archives.

I found [this BMS](https://forum.xentax.com/viewtopic.php?f=10&t=3950#p34056) but apparently it was made for another platform since my Saboteur.pck has different endian (that's why its identifier is "PCK1" instead of "1KCP").

Goodbye and thanks in advance!
## Post #2
- Username: ponaromixxx
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Jul 17, 2014 11:52 am
- Post datetime: 2019-10-21T03:08:40+00:00
- Post Title: The Saboteur (Xbox 360) nonstandard Wwise *.pck ("PCK1" identifier)

bnk_scan.bms

```
get FILE_SIZE asize
findloc OFFSET binary "BKHD"
math i = 1
for OFFSET = OFFSET < FILE_SIZE
  goto OFFSET
  get DUMMY long
  findloc NEXT_OFFSET binary "BKHD" 0 ""
  if NEXT_OFFSET == ""
   get NEXT_OFFSET asize
  endif
  xmath SIZE "NEXT_OFFSET - OFFSET"
  get NAME basename
  string NAME += "_"
  string NAME += i
  string NAME += ".bnk"
  log NAME OFFSET SIZE
  math OFFSET = NEXT_OFFSET
next i
```


Wwise_extract_bnk.bms

```
getDstring IDENT 4
if IDENT == "BKHD"
	callfunction BKHD 1
else
	print "Error: no valid Wwise bnk"
	cleanexit
endif

startfunction BKHD
	get TEST short
	set REV 0
	if TEST == 0
		set REV 1
		endian big
	endif
	goto 4
	get SIZE_HEADER long
	savepos MYOFF
	math MYOFF += SIZE_HEADER
	get FSIZE asize
	if MYOFF == FSIZE
		print "bnk is empty"
		cleanexit
	endif
	goto MYOFF
	idstring "DIDX"
	get SIZE_DIDX long
	set FILES SIZE_DIDX
	math FILES /= 0xc
	set BIAS MYOFF # complete header
	math BIAS += SIZE_DIDX
	math BIAS += 16
	get BNAME basename
	for i = 1 <= FILES
		get DIDX long
		get OFFSET long
		math OFFSET += BIAS
		get SIZE long
		set NAME DIDX
		string NAME p= "%s.wem" DIDX EXT
		log NAME OFFSET SIZE
	next i
endfunction
```
## Post #3
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2019-10-21T18:39:41+00:00
- Post Title: The Saboteur (Xbox 360) nonstandard Wwise *.pck ("PCK1" identifier)

It's much appreciated man, your script works nicely!

I wouldn't mind some help with properly extracting contents of [one of those *.bnk files](https://drive.google.com/open?id=1D_Ob9ubI-hEay4Bjx4ErFCx9p6ZUlGDT) though; it looks like there's a succession of many tracks after an actual bank (the one with "BKHD" identifier) here, that bank (Saboteur_338.bnk) is 433 МB but if I unpack it with Wwise_extract_bnk.bms I only get 784 КB worth of *.wem files. It'd be great if you helped me with proper extraction of Saboteur_338.bnk too!

Best regards & thank you once again!
## Post #4
- Username: ponaromixxx
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Jul 17, 2014 11:52 am
- Post datetime: 2019-10-22T02:41:16+00:00
- Post Title: The Saboteur (Xbox 360) nonstandard Wwise *.pck ("PCK1" identifier)

Need a whole file Saboteur_338.bnk for analysis
## Post #5
- Username: ponaromixxx
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Jul 17, 2014 11:52 am
- Post datetime: 2019-10-22T02:59:38+00:00
- Post Title: The Saboteur (Xbox 360) nonstandard Wwise *.pck ("PCK1" identifier)

wem-xma_scan.bms

```
findloc OFFSET binary "\x52\x49\x46\x58"
math i = 1
for OFFSET = OFFSET < FILE_SIZE
  goto OFFSET
  get DUMMY long
  findloc NEXT_OFFSET binary "\x52\x49\x46\x58" 0 ""
  if NEXT_OFFSET == ""
   get NEXT_OFFSET asize
  endif
  xmath SIZE "NEXT_OFFSET - OFFSET"
  get NAME basename
  string NAME += "_"
  string NAME += i
  string NAME += ".wem"
  log NAME OFFSET SIZE
  math OFFSET = NEXT_OFFSET
next i
```
