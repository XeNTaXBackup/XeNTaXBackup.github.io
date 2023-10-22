## Post #1
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2013-11-05T14:45:11+00:00
- Post Title: Groove Player .grv

I'm trying to get the files out the SpongeBob SquarePants Movie 3D Game, and the whole archive is in a file called "code.grv". Game Extractor only gets a few textures.
[https://www.dropbox.com/s/rdl5iqadqsgakpt/code.grv](https://www.dropbox.com/s/rdl5iqadqsgakpt/code.grv)
## Post #2
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-11-05T21:36:06+00:00
- Post Title: Groove Player .grv

This quickbms script can unpack

```
get tablesize1 long
get unk long
get tablesize2 long
get root string
get files long
for i = 0 < files
get unk long
get offset long
get zsize long
get name string
set temp name
string temp $ zlib
if temp = "zlib"
string name -= ".zlib"
math zsize -= 4
savepos off
goto offset
get size long
savepos offset
clog name offset zsize size
goto off
else
log name offset zsize
endif
next i
```
