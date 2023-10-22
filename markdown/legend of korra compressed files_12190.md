## Post #1
- Username: ss33
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Nov 01, 2014 5:20 pm
- Post datetime: 2014-11-03T14:38:30+00:00
- Post Title: legend of korra compressed files

hi everybody

i am trying to translate legend of korra game.how do i open .cbm .wta .bnk .eff .exp .sop .bxm file extensions

i am searching in the internet but i didn't found.

sorry for bad english.
## Post #2
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-11-12T09:17:44+00:00
- Post Title: legend of korra compressed files

Post some sample files please.
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2015-01-15T13:14:22+00:00
- Post Title: legend of korra compressed files

> Reply from gregkwaste
>
> Post some sample files please.
[http://ikskoks.playloc.pl/XENTAX/Legend ... amples.rar](http://ikskoks.playloc.pl/XENTAX/Legend%20of%20Korra%20samples.rar)
[http://ikskoks.playloc.pl/XENTAX/Legend ... mples2.rar](http://ikskoks.playloc.pl/XENTAX/Legend%20of%20Korra%20samples2.rar)
Any samples you need
## Post #4
- Username: dniel888
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 17, 2014 7:01 am
- Post datetime: 2015-01-16T00:21:05+00:00
- Post Title: legend of korra compressed files

I have created a script for extractiong all files with "DAT\0" header:

```
# (c) 16/01/2015 by dniel888
# script for QuickBMS http://quickbms.aluigi.org

IDString "DAT\x00"

get FILESNUM long

get OFFSETPOS long
get EXTPOS long
get STRINGPOS long
get SIZEPOS long
get UNKPOS long

get ZERO long

goto OFFSETPOS
for i = 0 < FILESNUM
	get OFFSET[i] long
next i

goto SIZEPOS
for i = 0 < FILESNUM
	get SIZE[i] long
next i

goto STRINGPOS
get STRINGSIZE long
for i = 0 < FILESNUM
	getDstring NAME STRINGSIZE
	log NAME OFFSET[i] SIZE[i]
next i

cleanexit




```
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2015-01-21T10:56:48+00:00
- Post Title: legend of korra compressed files

Thank you
