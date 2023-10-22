## Post #1
- Username: gtaneverdie
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 30, 2010 12:33 am
- Post datetime: 2011-01-12T11:31:49+00:00
- Post Title: Judge Dredd asr file

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-12T16:33:19+00:00
- Post Title: Judge Dredd asr file

so have you actually tried an extractors for those games?

this format has a lot of block headers which would be painful to parse from scratch   

pseudocode!

```

inf loop:
block_id (if block_id = "" the exit)
block_size
++ block data ++

the block_id order of sample (note the NUMBER OF BLOCK HEADERS TO READ..):
RSFL
RSCF
TEXT
TXFL
MSHV
MSHP
MTXT
MSMG
HSKN
HMPT
HSBB
RSCF
ATBL
ATBL
ATBL
HCAN
ATBL
ATBL
HCAN
ATBL
ATBL
HCAN
PTXT
PTXT
PTXT
PTXT
PTXT

```
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-01-12T22:39:30+00:00
- Post Title: Judge Dredd asr file

[http://aluigi.org/papers/bms/asura.bms](http://aluigi.org/papers/bms/asura.bms)
## Post #4
- Username: gtaneverdie
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 30, 2010 12:33 am
- Post datetime: 2011-01-13T11:20:56+00:00
- Post Title: Judge Dredd asr file

thanks!both of you
