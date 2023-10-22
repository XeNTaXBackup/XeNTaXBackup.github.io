## Post #1
- Username: XAION
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 18, 2010 11:12 pm
- Post datetime: 2010-10-06T10:15:53+00:00
- Post Title: (PS3) Darksiders OBPK packages

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-10-06T19:50:45+00:00
- Post Title: (PS3) Darksiders OBPK packages

along with the filelist are either folder names or resource types.
as i cant determine which is which, these are nameless  but hopefully i can get it completely working 

there is also a minor issue with skipping the position pointers with things which arent files.
> so this script will only work with lurcher.opps3 for now. only the "FOLDERSKIP" part needs updating to dump everything else.


so yeah, nameless files atm, but split up 
will try to work on it more later

edit: sorry about these excessive paragraphs - must be some encoding issue with firefox - edited it now

```

# "psystem" are BOD files
# "mp3" is FSB

endian big

## Header

idstring "OBPK"
getdstring UNKNOWN 14
get NSTRUCTPOINTER long # >= 30
get DATAPOINTER long    # next 4096 block - NSTRUCTPOINTER

## EStruct (only in scythe.opps3 from the few examples i had -
#           though has the same structure as NStruct)

get ESTRUCTCOUNT long

for i = 0 < ESTRUCTCOUNT
  getdstring UNKNOWN 8
  get NAMELEN long
  getdstring NAME NAMELEN
next i

## NStruct
# goto NSTRUCTPOINTER

get NSTRUCTCOUNT long

for i = 0 < NSTRUCTCOUNT
  getdstring UNKNOWN 8
  get NAMELEN long
  getdstring NAME NAMELEN
next i

## ZLib data chunks

savepos LASTPOS
math DATASTART = DATAPOINTER
math DATASTART += NSTRUCTPOINTER
goto DATASTART

get ZSIZE long
savepos POS
get SIZE asize
math SIZE -= POS

# the opps3 files are small enough to make this ok
clog MEMORY_FILE POS SIZE ZSIZE

## Split files
goto LASTPOS

get NULL long
get FOLDERS long # actually resource type, not folder
math FOLDERSKIP = FOLDERS
math FOLDERSKIP *= 10 # NOTE: 10 IS FOR lurcher file ONLY - OTHER FILES ARE DIFFERENT (not completely reversed)

getdstring UNKNOWN FOLDERSKIP
get UNKNOWN long
math FILECNT = ESTRUCTCOUNT
math FILECNT += NSTRUCTCOUNT
math FILECNT -= FOLDERS

print "Exporting %FILECNT% files (there are references to %FOLDERS% types)!"
math MEMOFFSET = 0

for i = 0 < FILECNT
  getdstring UNKNOWN 8
  get SIZE1 long
  get BYTE4 byte
  get SIZE2 long
  get NULL long
  log "" MEMOFFSET SIZE1 MEMORY_FILE
  math MEMOFFSET += SIZE1
next i
```
## Post #3
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2010-10-11T14:36:16+00:00
- Post Title: (PS3) Darksiders OBPK packages

It seems quite interesting...... if I remember well , this game is based on unreal engine 3 ,right? Maybe Gildor 's tool could help...
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-10-11T17:22:53+00:00
- Post Title: (PS3) Darksiders OBPK packages

op just needs to respond for me to bother finishing it. another tool would defeat the point of this tread - op wanted to learn more about how this file format stored the offsets.
## Post #5
- Username: prudislav
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 13, 2010 6:48 am
- Post datetime: 2010-10-13T16:02:21+00:00
- Post Title: (PS3) Darksiders OBPK packages

do you have a script for PC files???
## Post #6
- Username: godinhochina
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 22, 2009 6:00 am
- Post datetime: 2010-10-13T22:52:49+00:00
- Post Title: (PS3) Darksiders OBPK packages

I wanna translate this game for the PT-BR language to a web site in Brazil called [http://www.gamevicio.com.br](http://www.gamevicio.com.br), so if anyone else here find a tool, please send it to my email:
[augustogodinho@hotmail.com](mailto:augustogodinho@hotmail.com)
## Post #7
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2010-11-11T09:37:28+00:00
- Post Title: (PS3) Darksiders OBPK packages

Any news about extracting the models from this game?
