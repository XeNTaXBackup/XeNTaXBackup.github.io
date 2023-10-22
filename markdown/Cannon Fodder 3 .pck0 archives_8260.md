## Post #1
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2012-02-12T00:19:50+00:00
- Post Title: Cannon Fodder 3 .pck0 archives

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-12T00:28:51+00:00
- Post Title: Cannon Fodder 3 .pck0 archives

```
get unk long
get files long
get unk long
for i = 0 < files
get hash long
getdstring NAME 0xF0
get offset long 
get zsize long
get size long
if zsize == size
log NAME offset size
else
clog NAME offset zsize size
endif
next i

```
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-12T00:46:43+00:00
- Post Title: Cannon Fodder 3 .pck0 archives

I wrote the script for this game various days ago, I inserted it in the other_bms_scripts.zip package:
[http://aluigi.org/papers/bms/other_bms_scripts.zip](http://aluigi.org/papers/bms/other_bms_scripts.zip)

my doubt is about the log/clog function, are we sure that some files aren't compressed?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-12T02:04:45+00:00
- Post Title: Cannon Fodder 3 .pck0 archives

no i just put it there in case.
dint know it was already done sorry
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-12T11:04:18+00:00
- Post Title: Cannon Fodder 3 .pck0 archives

eh eh eh sorry of what?
it was impossible to know that the zip contained the script.

I need to find an alternative way for the scripts in others_bms_scripts.zip otherwise they can't be indexed and found by the people...
