## Post #1
- Username: Allen
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Feb 17, 2012 4:49 pm
- Post datetime: 2012-08-11T03:03:45+00:00
- Post Title: about quickbms recompression zlib_compress type

I am now working on the localization of a game.
I need use quickbms re-zlibcompress file.
game original file use zlib standard compression :789C.
I write a script recompress file.but Compressed file is  is 78DA(compression extreme)，not 789C.

```
get size asize
log MEMORY_FILE 0 0
put size long MEMORY_FILE	#write uncompress size
get name filename
append
clog MEMORY_FILE 0  size size
append
get size asize MEMORY_FILE 
log name 0 size MEMORY_FILE 
```


How can I changed to 789C?

sorry my bad english.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-12T23:48:24+00:00
- Post Title: about quickbms recompression zlib_compress type

why you would do it?

that sequence of bytes contains info about the compression like the used algorithms and the compression level.
note that it doesn't affect the decompression algorithms.
## Post #3
- Username: Allen
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Feb 17, 2012 4:49 pm
- Post datetime: 2012-08-13T01:03:08+00:00
- Post Title: about quickbms recompression zlib_compress type

yes,aligui!Thanks for your reply!
You are right！ The game support 78DA.
In my tests, it also proves this point.
