## Post #1
- Username: Aroenai
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 12, 2011 10:05 am
- Post datetime: 2011-10-12T22:24:44+00:00
- Post Title: King's Quest 8 Mask of Eternity .vol files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Aroenai
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 12, 2011 10:05 am
- Post datetime: 2011-11-02T17:52:24+00:00
- Post Title: King's Quest 8 Mask of Eternity .vol files

bump

Thinking it's a variation of this: [http://wiki.scummvm.org/index.php/SCI/S ... CL-EXPLODE](http://wiki.scummvm.org/index.php/SCI/Specifications/Resource_files/Decompression_algorithms/DCL-EXPLODE)

Please I need some help.
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-11-03T02:35:51+00:00
- Post Title: King's Quest 8 Mask of Eternity .vol files

i though i'd already written a script for this thread    so im a bit confused

anywho its not crashing with quickbms set to explode (!!)
here you are:

```

comtype explode

get FNAME basename
get FSIZE asize

for

  getdstring RESNAME 20
  get NXTRES long
  savepos RESPOS
  math RESSIZE = NXTRES
  math RESSIZE -= RESPOS

  string RESFN p= "%s\%s" FNAME RESNAME

  #print "%RESNAME% == %RESSIZE% @ %RESPOS%"

  clog RESFN RESPOS RESSIZE 0xFFFF

  if NXTRES == FSIZE
    cleanexit
  else
    goto NXTRES
  endif

next

```
## Post #4
- Username: Aroenai
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 12, 2011 10:05 am
- Post datetime: 2011-11-04T07:11:50+00:00
- Post Title: King's Quest 8 Mask of Eternity .vol files

The contents of this post was deleted because of possible forum rules violation.
