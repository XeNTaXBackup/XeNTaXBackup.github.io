## Post #1
- Username: Polefish
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-05-30T23:58:00+00:00
- Post Title: Summon Night 5 PSP

```
set counter 0
get tsize asize
for
set name counter
goto offset
get magic long
if magic == 0x46464952
string name + ".at3"
get size long
math size + 8
elif magic == 0x10040101
string name + ".type1"
getdstring null 8
get size long
math size + 12
elif magic == 0x10000301
string name + ".type2"
getdstring null 4
get size long
elif magic == 0x10000101
string name + ".type3"
getdstring null 4
get size long
elif magic == 0
string name + ".type0"
getdstring null 0x40
get size long
set tmp offset
math tmp + size
goto tmp
getdstring null 0x10
get size long
math size + 0x10
elif magic == 0x10003101
string name + ".type4"
getdstring null 4
get size long
else
print "%magic%"
cleanexit
endif
log name offset size
math offset + size
goto offset
Padding 2048
savepos offset
math counter += 1
if offset == tsize
cleanexit
endif
next

```
