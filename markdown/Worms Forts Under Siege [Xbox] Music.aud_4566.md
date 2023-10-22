## Post #1
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-06-06T18:01:14+00:00
- Post Title: Worms Forts Under Siege [Xbox] Music.aud

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-08T20:05:52+00:00
- Post Title: Worms Forts Under Siege [Xbox] Music.aud

I added a counter to the end  because of duplicate files or variations.

```
get ZERO long
get UNKNOWN long
get FILES long
get UNKNOWN long

for i = 1 <= FILES
	get ZERO long
	get ZERO long
	get ZERO long
	get UNKNOWN long
	get ZERO long
	get ZERO long
	get UNKNOWN long
	get NAMEPOS long
		math NAMEPOS += 8
		savepos OFF
		goto NAMEPOS
		get NAME string
		goto OFF
	get INFOPOS long
	get OFFSET long
	get SIZE long
	get UNKNOWN long
	get UNKNOWN long
	get UNKNOWN long
	get ZERO long
	get ZERO long
	get UNKNOWN long
	string NAME += "_"
	string NAME += i
	log NAME OFFSET SIZE
next i
```
## Post #3
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-06-08T20:15:03+00:00
- Post Title: Worms Forts Under Siege [Xbox] Music.aud

Thanks for scripty mate
