## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-20T21:57:16+00:00
- Post Title: The Castle of Dawn (曙光之城)

I think another game also uses the same archive format, but ya.

```
idstring "OMPF"
get null long
get TABLE_OFS long

goto TABLE_OFS

do
	get unk long
	getdstring NAME 256
	get SIZE long
	get OFFSET long
	get ZSIZE long
	if SIZE != ZSIZE
		print "%NAME% compressed"
	endif
	log NAME OFFSET SIZE
while unk = 2

```
