## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-22T17:55:17+00:00
- Post Title: Valkyrie: Ascension To The Thrown

```
#Quickbms
#By:Chrrox

get GRES long
get version long
get files long
for i = 0 < files
getdstring name 0x80
get offset long
get size long
log name offset size
next i
```
