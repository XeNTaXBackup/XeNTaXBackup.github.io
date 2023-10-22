## Post #1
- Username: KuchiBoy
- Rank: Banned
- Number of posts: 21
- Joined date: Wed May 23, 2012 3:35 am
- Post datetime: 2012-06-15T20:25:42+00:00
- Post Title: WINtA Music (.dat)

The game WINtA for iphone has these music tracks in them, but they're .dat. The audio, when imported to audacity raw, doesn't work - of course. Game Extractor's scan only finds images from the game, but considering it's 8.99 MB, I doubt it's only images. 

I would post a sample but I've been banned for that with another account, so I'll just tell you how to find it. 

The game's free on the app store, and the song I'm trying to rip from is Funny Luv, which is also a free download. The tool iFunBox or any other ios explorer should work too, but the one I used is iFunBox.
To get it in iFunBox:
Connected Devices/(idevice name)/User Applications/Winta/Library/caches/tracks

Alternatively, you can PM me and I'll link you.
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-06-20T00:01:25+00:00
- Post Title: WINtA Music (.dat)

Crappy format... Used many workarounds to get anything at all.
Ok, first you'll need to split up the dat file with my gensplit script here: [viewtopic.php?f=13&t=4450&p=45460#p45460](http://forum.xentax.com/viewtopic.php?f=13&t=4450&p=45460#p45460)
Variables are OFFSET 0, SKIP 0 NEGBIAS 0, the searchstring is "War Is Not the Answer". Set the extension to ".winta".
Second, you use the below script on the first big *.winta. You'll need the newest func_getTYPE.bms to have those *.m4a files identified: [viewtopic.php?f=13&t=4450&p=69577#p69577](http://forum.xentax.com/viewtopic.php?f=13&t=4450&p=69577#p69577). Just save it in the same folder as the below script.

```
idstring "War Is Not the Answer"
get FSIZE asize
goto 0x66
for i = 1
	get SIZE long
	savepos OFFSET
		set TEST OFFSET
		math TEST += SIZE
		math TEST -= 8
		goto TEST
		getDstring IDENT 4
		if IDENT == "IEND"
			set BIAS 0
		else
			set BIAS 4
		endif
	get NAME basename
	string NAME += "_"
	string NAME += i
		set TEST OFFSET
		math TEST -= 0xa
		goto TEST
		get ENDTEST short
		if ENDTEST == 0x0a0d # write residuum
			get SIZE asize
			math SIZE -= OFFSET
		endif
	log MEMORY_FILE OFFSET SIZE
	callfunction getTYPE 1
	string NAME += EXT
	log NAME 0 SIZE MEMORY_FILE
	math OFFSET += SIZE
	math OFFSET += BIAS
	if OFFSET >= FSIZE
		cleanexit
	endif
	goto OFFSET
	do
		get TEST long
	while TEST <= 0x10
	savepos MYOFF
	math MYOFF -= 4
	goto MYOFF
next i
```

This is only for the first bigger file (13.7 MB). Names are not given, the format is really engine-specific. There are some *.png files, the file before the last can be opened with Notepad to see some matrix and the last one is unknown data.
If you still have any questions, just ask here.
## Post #3
- Username: KuchiBoy
- Rank: Banned
- Number of posts: 21
- Joined date: Wed May 23, 2012 3:35 am
- Post datetime: 2012-06-20T22:46:22+00:00
- Post Title: WINtA Music (.dat)

> Reply from AlphaTwentyThree
>
> the searchstring is "War Is Not the Answer".

Sorry for sounding like an idiot, but I have no idea what to change for the searchstring.
I'm using the song Funny Luv, not War Is Not The Answer, so it's something completely different.

What I've done so far:

```
set SKIP 0 # skip bytes at start of search string (use negative value if identifier is after file start)
set NEGBIAS 0x0 # search string at end of file e.g. stop markers
set EXT ".winta"

set SEARCH OFFSET
set QUIT 0
set SINGLE 0
set i 0
FindLoc SIZE string "Funny Luv (FREE)" ""

```


This makes the .winta, but there's only one, and it's the same size as the original. using the script you posted, gives an error, and makes nothing.
Again, sorry for sounding stupid, but I'm not the best with quickbms :p
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-06-21T12:09:43+00:00
- Post Title: WINtA Music (.dat)

> Reply from KuchiBoy
>
> I'm using the song Funny Luv, not War Is Not The Answer, so it's something completely different.
That's the answer to your question. Any other searchstring will return other results. The script splits files at the given searchstring.
## Post #5
- Username: KuchiBoy
- Rank: Banned
- Number of posts: 21
- Joined date: Wed May 23, 2012 3:35 am
- Post datetime: 2012-06-21T16:47:27+00:00
- Post Title: WINtA Music (.dat)

Okay, I realize what I did wrong, I was setting it to "Funny Luv (FREE)" because that's what it's named in the app, when it's actually just "Funny Luv". But there's another problem..

Error: incomplete input file number 0, can't read 4 bytes.

And it finds nothing. The file has been split into the three files, one 48 bytes, one 8.9 MB (I'm assuming this is it) and one 298 KB.
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-06-21T17:28:30+00:00
- Post Title: WINtA Music (.dat)

I don't know what's so hard to understand:

```
set SKIP 0
set NEGBIAS 0x0
set EXT ".winta"

set SEARCH OFFSET
set QUIT 0
set SINGLE 0
set i 0
do
	goto SEARCH
	FindLoc SIZE string "War Is Not the Answer" 0 ""
	if SIZE == ""
		set QUIT 1
		get SIZE asize
		if i == 0
			goto 0
			set SINGLE 1
		endif
	endif
	if SIZE == 0 # no residual data at start
		math i += 1
	endif
	math SIZE -= OFFSET
	if SIZE > 4
		get NAME basename
		if SINGLE != 1
			string NAME += "_"
			if i < 100
				string NAME += "0"
				if i < 10
					string NAME += "0"
				endif
			endif
			string NAME += i
			if i != 0
				string NAME += EXT
			endif
		else
			string NAME += EXT
		endif
		if QUIT != 1
			math SIZE += SKIP
			math SIZE += NEGBIAS
		endif
		log NAME OFFSET SIZE
		math i += 1
	endif
	if QUIT != 1
		math OFFSET += SIZE
		set SEARCH OFFSET
		math SEARCH += 4 # needs to be the length of the search string
		if SKIP < 0
			math SEARCH -= SKIP
		endif
	endif
while QUIT != 1
```
## Post #7
- Username: KuchiBoy
- Rank: Banned
- Number of posts: 21
- Joined date: Wed May 23, 2012 3:35 am
- Post datetime: 2012-06-21T18:15:07+00:00
- Post Title: WINtA Music (.dat)

Well, I tried this method on the file winta.dat in the .ipa, and it works flawlessly. It just isn't working on Funny Luv.
