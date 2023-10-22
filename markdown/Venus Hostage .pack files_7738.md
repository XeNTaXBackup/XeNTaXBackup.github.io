## Post #1
- Username: LordRius
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Apr 01, 2011 5:48 pm
- Post datetime: 2011-11-23T17:55:25+00:00
- Post Title: Venus Hostage .pack files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-12-03T20:29:03+00:00
- Post Title: Venus Hostage .pack files

not going any further but the parts (unordered - ignore the filenames) can be read like:

```
get PNUM long

get POS asize
math TMP = PNUM
math TMP *= 13
math TMP += 4
math POS -= TMP
goto POS

for i = 0 < PNUM
  # 13 byte header
  getdstring MISC 5 # options?
  get PNTR long
  get SIZE long
  string NAME p= "part_%03i.jc" i
  log NAME PNTR SIZE
next i

```
