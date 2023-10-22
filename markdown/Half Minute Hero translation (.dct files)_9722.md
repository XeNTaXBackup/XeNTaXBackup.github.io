## Post #1
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2012-10-09T16:45:01+00:00
- Post Title: Half Minute Hero translation (.dct files)

Hi there!

Half Minute Hero has been released on PC, and I'd like to translate it to my language. I've seen the files, and the text is in .dct files. There are some smaller text in .bin files too, but most of it is in the .dct's.

Who can help me with these files, and how can I help you (posting some of the files or some part of them or what)?
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-10-10T15:45:11+00:00
- Post Title: Half Minute Hero translation (.dct files)

i found the game online.


the extensions used by the game can be ignored.
some .bin files (TextTable_xx.bin) contain null-terminated strings
other formats can be extracted with this script:

```
# QuickBMS script by WRS

get size asize

do
  getdstring name 24
  getdstring ext 4
  get size long
  savepos pos
  string fname p= "%s.%s" name ext
  log fname pos size
  math pos += size
while pos < size

```

note some files have several 'containers' before the actual data. to save yourself time extracting, run quickbms from the command line if you can

edit
cscv format (poc parser, does not extract anything)

```
get itemSize long # 284
get itemCnt long # n
get NEGONE long # -1

for i = 0 < itemCnt
  get int1 long # 30000 ?
  get int2 long # 0 
  get int3 long # -1
  get int4 long # 199/200
  get int5 long # ~10
  get int6 long # <5
  getdstring STR1 64 # scene 
  getdstring STR2 64 # empty
  getdstring STR3 64 # empty
  getdstring STR4 64 # empty
  get NEGONE long # -1
next i

```
## Post #3
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2012-10-11T16:53:33+00:00
- Post Title: Half Minute Hero translation (.dct files)

Thank you for your answer, but the first script tells me this when I run it on any file (be it .dct or anything else):

"Invalid operator p"

I tried the other one as well, but it said "0 files" on everything I tried it on :\
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-10-11T23:24:50+00:00
- Post Title: Half Minute Hero translation (.dct files)

whoops, the first script should look like:

```

do
  getdstring name 24
  getdstring ext 4
  get size long
  savepos pos
  string fname f= "%s.%s" name ext
  log fname pos size
  math pos += size
  goto pos
while pos < size

```


and i said the second script doesn't extract anything..
## Post #5
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2012-10-12T13:03:44+00:00
- Post Title: Half Minute Hero translation (.dct files)

Thanks for the reply, but this also doesn't work, says "Invalid operator f"

BTW can this export and import text too?
