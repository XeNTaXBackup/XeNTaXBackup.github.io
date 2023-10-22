## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-05T11:33:57+00:00
- Post Title: Strike Base GAMEDATA File (*.CD, *.HD?)

I wrote a script for this kind of format. I thought I might share it with you. Maybe someone can find it through the search.
Game is from 1996 already but hey, reversing is reversing, right? 

```

callfunction getfiles 1
goto 0xb0

for i = 1 <= FILES
	getDstring HD 2
	getDstring NAME 0x26
	get OFFSET long
	get SIZE long # end offset
	math SIZE -= OFFSET
	log NAME OFFSET SIZE
next i

startfunction getfiles
	goto 0xb0
	set FILES 0
	for FILES = 0
		getDstring TEST 2
		if TEST != "d:"
			break
		else
			savepos OFF
			math OFF += 0x2e
			goto OFF
		endif
	next FILES
endfunction
```
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-05T11:43:44+00:00
- Post Title: Strike Base GAMEDATA File (*.CD, *.HD?)

The contents of this post was deleted because of possible forum rules violation.
