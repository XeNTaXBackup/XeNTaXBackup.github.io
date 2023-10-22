## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-10-05T21:46:16+00:00
- Post Title: d5online

Here is a pac extractor for this game.
[http://hm.d5online.com/web_v1/download_01.html](http://hm.d5online.com/web_v1/download_01.html)

```
#by chrrox
idstring "PGFN"
get version long
goto 0x18
get files long
for i = 0 < files
get nsize long
get offset long
get size long
get nextoff long
getdstring name nsize
log name offset size
goto nextoff
next i

```
## Post #2
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-10-05T21:51:10+00:00
- Post Title: d5online

nice!

.smd files inside, checking them now
