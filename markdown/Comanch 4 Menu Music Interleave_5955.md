## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-01-31T01:44:46+00:00
- Post Title: Comanch 4 Menu Music Interleave

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2011-02-01T17:47:02+00:00
- Post Title: Comanch 4 Menu Music Interleave

Have you ever looked at this file in hex? This is an archive including 157 files... Of course any interleave will fail...

Anyway, here's an extractor:

```
get UNK long
get CODEC long # normally IMA ADPCM
get ZERO long
get UNK long
get FILES long
for i = 1 <= FILES
	getDstring NAME 0x10
	get OFFSET long
	get SIZE long
	get UNK long
	get UNK long
	log NAME OFFSET SIZE
next i
```

Offset seems to be 0x800 bytes.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-01T20:07:32+00:00
- Post Title: Comanch 4 Menu Music Interleave

Thanks.

still cant get the files to play correctly. though
