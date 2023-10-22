## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-11T03:32:00+00:00
- Post Title: Demons Code

Here is a pac extractor for this game
[http://gamespace24.net/demons/](http://gamespace24.net/demons/)

```
goto 0x1C
for i = 0 < files
getdstring name 0x20
get offset long
get size long
get hash long
get unk01 long
log name offset size
next i

```
