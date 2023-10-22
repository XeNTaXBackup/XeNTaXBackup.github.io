## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-04-09T19:14:26+00:00
- Post Title: Blood Omen 2 PS2.RKV

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-04-11T20:33:17+00:00
- Post Title: Blood Omen 2 PS2.RKV

Anyone?
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-11T21:01:10+00:00
- Post Title: Blood Omen 2 PS2.RKV

```
get tablesize long
get unk01 long
get fldrsize long
getdstring folder fldrsize
string folder + \
get unk02 long
get fldr2size long
getdstring folder2 fldr2size
string folder + folder2
string folder + \
get files long
for i = 0 < files
set name folder
get null long
get namesize long
getdstring name2 namesize
get null long
get offset long
get size long
math offset * 0x800
math offset + 0x1a000
string name + name2
string name + .wav
log name offset size
next i

```
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-04-11T22:02:04+00:00
- Post Title: Blood Omen 2 PS2.RKV

Thanks!!
