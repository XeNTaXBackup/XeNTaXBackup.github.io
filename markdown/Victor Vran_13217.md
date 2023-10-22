## Post #1
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-08-19T22:59:09+00:00
- Post Title: Victor Vran

Hi guys, installed Victor Vran today, not all that bad for a game, wanted to check on the models, unfortunatly it is all packed into .hpk files.

And since I have no idea how to unpack these, I was wandering if some genius would be able to help me with it plz ?

Here is a small sample

T.
## Post #2
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2015-08-20T08:02:12+00:00
- Post Title: Victor Vran

> Reply from TaylorMouse
>
> Hi guys, installed Victor Vran today, not all that bad for a game, wanted to check on the models, unfortunatly it is all packed into .hpk files.

And since I have no idea how to unpack these, I was wandering if some genius would be able to help me with it plz ?

Here is a small sample

T.
Since the engine it's based on is the same as Tropico 5, you can use this to unpack and repack .hpk archives (tested):
[http://www.techpowerup.com/forums/threa ... er.113705/](http://www.techpowerup.com/forums/threads/tropico-3-4-5-hpk-archiver.113705/)
## Post #3
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-08-20T10:03:40+00:00
- Post Title: Victor Vran

Yes that seems to be working thanx !!

T.
## Post #4
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2017-06-08T21:59:35+00:00
- Post Title: Victor Vran

New update out and files inside *.hpk now are compressed with lz4, so first unpack *.hpk with hpk-archiver and then use this script on files

```
comtype lz4
get SIZE long
get CHUNK_SIZE long
get NAME filename
xmath TMP "SIZE % CHUNK_SIZE"
if TMP != 0
	math TMP = 1
else
	math TMP = 0
endif
xmath CHUNKS "(SIZE / CHUNK_SIZE) + TMP"
append
for i = 1 <= CHUNKS
	get OFFSET long
	savepos POS
	if i == CHUNKS
		get ZSIZE asize
	else
		get ZSIZE long
	endif
	math ZSIZE -= OFFSET
	goto POS
	if ZSIZE < CHUNK_SIZE
		clog NAME OFFSET ZSIZE CHUNK_SIZE
	else
		log NAME OFFSET ZSIZE
	endif
next i
append

```
