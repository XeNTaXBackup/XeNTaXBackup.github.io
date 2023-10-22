## Post #1
- Username: felixthekat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 15, 2011 11:20 pm
- Post datetime: 2011-04-01T02:24:49+00:00
- Post Title: Pak files (MIS)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2011-04-01T12:30:30+00:00
- Post Title: Pak files (MIS)

```
# QuickBMS script for "The Fool" .PAK files
# created by The Bacter
#############################################################################
idstring "MIS"
getdstring DUMMY 5
get DUMMY long
get NR_OF_FILES long
get DUMMY byte
get SUBBYTE byte
getdstring DUMMY 14
set MINUS byte 256
math MINUS -= SUBBYTE
filerot MINUS
for i = 0 < NR_OF_FILES
  getdstring FILE_NAME 64
  get FILE_SIZE long
  get FILE_POS long
  get UNKNOWN long
  log FILE_NAME FILE_POS FILE_SIZE
next i

```
