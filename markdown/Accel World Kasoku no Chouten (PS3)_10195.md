## Post #1
- Username: finale00
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-03-05T01:27:33+00:00
- Post Title: Accel World Kasoku no Chouten (PS3)

Here is a quickbms script for this games dat files.
[http://accel-world-game.channel.or.jp/](http://accel-world-game.channel.or.jp/)
アクセル・ワールド -加速の頂点

```
#Accel World Kasoku no Chouten (PS3)
idstring "GPDA"
get tsize longlong
get files long
savepos tmp
for i = 0 < files
goto tmp
get offset long
get comp long
get size long
get nameoff long
savepos tmp
goto nameoff
get nsize long
getdstring name nsize
if comp == 1
string name + .gz
endif
log name offset size
next i

```
## Post #2
- Username: weling2010
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Feb 10, 2012 3:35 pm
- Post datetime: 2013-08-21T06:56:53+00:00
- Post Title: Accel World Kasoku no Chouten (PS3)

how open fmdl or fmnt from union dat?
