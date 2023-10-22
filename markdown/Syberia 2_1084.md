## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-02-11T15:47:39+00:00
- Post Title: Syberia 2

hello

this is syberia 2 arrchive

thanks
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-12T11:27:00+00:00
- Post Title: Syberia 2

Hey,

I couldn't find anything in these files at all - however it was interesting that the larger of the files had a common structure something like this...

```
14 - Data
```


This structure is repeated through the entire file (i think) - but it doesn't look to me like an archive. Guess we will see if Mr Mouse comes up with anything.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-02-12T15:32:12+00:00
- Post Title: Syberia 2

mr watto

all packages include 3 file 

1. *.msb = include adpcm ps2 file (play with raw)
2. *.msh = unknow for me
3. *.slt    = file name list  for msb arrchive

above arrchive 4mb

Iam send you 1mb from arrchive

thanks
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-13T12:34:40+00:00
- Post Title: Syberia 2

OK, well I will take another look at it - see what I can get.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-13T22:19:39+00:00
- Post Title: Syberia 2

Nope, I still can't get anything to make any sense.

I can understand the structure of the *.slt files - they go something like this...

```
4 - null
4 - Number Of Files

// for each file
  X - Filename (null)
  4 - Unknown
  4 - File Size?
```


But there doesn't seem to be any connection between the files. For example, the SLT file you sent has a few files at the beginning of size 16, but then the rest of them are size 24 - this does not match with the data file because it is obvious that the file sizes should all be 16 - Basically there are conflicts between the data and directory files.

I dunno, I am stumped on this one 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
