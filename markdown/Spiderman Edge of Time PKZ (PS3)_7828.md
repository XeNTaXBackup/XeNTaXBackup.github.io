## Post #1
- Username: Milesgboy
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-08T21:56:32+00:00
- Post Title: Spiderman Edge of Time PKZ (PS3)

Here is a quickbms script to extract this game.

```
#Script by chrrox
#Quickbms by Luigi Auriemma http://aluigi.altervista.org/
endian big
comtype zlib_noerror
get idstring long
get chunksize long
get baseoff long
get unkown long
get files long
get totalzsize long
get totalsize long
get name filename
set offset baseoff
string name + .ext
savepos tmp
for i = 0 < files
if i == 0
get size long
else
goto tmp
get old long
savepos tmp
get size long
math size - old
endif
if totalzsize >= 0x8000
set zsize 0x8000
else
set zsize totalzsize
endif
append
clog name offset zsize size
append
math offset += 0x8000
math totalzsize - 0x8000
next i

```
## Post #2
- Username: SoapyLemons
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Feb 04, 2011 9:01 am
- Post datetime: 2011-12-17T07:00:31+00:00
- Post Title: Spiderman Edge of Time PKZ (PS3)

I'm quite interested in this. Do you plan to go further with this?
## Post #3
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2012-06-14T20:03:21+00:00
- Post Title: Spiderman Edge of Time PKZ (PS3)

Any chance we can see this be updated to have actual file names being used?
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-14T22:06:42+00:00
- Post Title: Spiderman Edge of Time PKZ (PS3)

I don't think so. When uncompressed the files do not contain a list of file names. The vertex data for this game is weird also so I doubt we will see any models from this anytime soon.
## Post #5
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2012-06-28T14:35:13+00:00
- Post Title: Spiderman Edge of Time PKZ (PS3)

I hope someone will try to get into this. Since this is the 3rd game from them so far since they released The Amazing Spider-Man and those models would be pretty sweet to look at.
