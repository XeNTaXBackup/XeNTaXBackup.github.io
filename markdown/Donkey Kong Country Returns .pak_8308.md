## Post #1
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2012-02-16T21:55:09+00:00
- Post Title: Donkey Kong Country Returns .pak

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2012-02-26T01:18:35+00:00
- Post Title: Donkey Kong Country Returns .pak

Nevermind.

If anyone wants the BMS code, here's to extract the RAS out of the PAKs in the game's "worlds" folder. If you want ambience and etc. Thanks to OrangeC for it.

```
string BNAME += "_"
set OFFSET 0
set SEARCH OFFSET
math SEARCH += 8
set QUIT 0
for i = 1
   goto SEARCH
   FindLoc SIZE string "\x52\x41\x53\x5F\x00\x00\x00\x02" 0 ""
   if SIZE == ""
      get SIZE asize
      set QUIT 1
   endif
   math SIZE -= OFFSET
   set NAME BNAME
   string NAME += i
   log NAME OFFSET SIZE
   if QUIT != 1
      math OFFSET += SIZE
      set SEARCH OFFSET
      math SEARCH += 8 # needs to be the lengh of the search string
   else
      cleanexit
   endif
next i
```
