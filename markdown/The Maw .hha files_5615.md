## Post #1
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2010-12-23T11:15:24+00:00
- Post Title: The Maw .hha files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-23T20:52:30+00:00
- Post Title: The Maw .hha files

compressed with some algorithm i don't know.
written just to test the quickbms array functions really   

```
goto 8

get STRSIZE long
get STRCOUNT long

for i = 0 < STRCOUNT
  get STR string
  putarray 0 i STR
next i

get UNKNOWN long
get UNKNOWN long

for i = 0 < STRCOUNT
  get UNKNOWN long # compression flag?
  get POINTER long
  get UNSIZE long
  get SIZE long
  get ZUNKNOWN long # true size?
  get UNKNOWN long

  getarray FNAME 0 i
  log FNAME POINTER SIZE

next i

```


mainly lua scripts though
## Post #3
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2010-12-24T08:29:12+00:00
- Post Title: The Maw .hha files

too many encrypted files anyway thanks for the script
