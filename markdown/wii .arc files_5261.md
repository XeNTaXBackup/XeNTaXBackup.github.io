## Post #1
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2010-10-21T14:45:10+00:00
- Post Title: wii .arc files

Hello, everybody.
Can anybody tell me how to extract .arc files.
[delete](delete)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-10-21T15:25:42+00:00
- Post Title: wii .arc files

say the name of the game
## Post #3
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2010-10-21T15:51:12+00:00
- Post Title: wii .arc files

> Reply from chrrox
>
> say the name of the game
From Super Robot Wars NEO

Thank you for your interest.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-10-21T19:11:25+00:00
- Post Title: wii .arc files

here is a quckbms script.

```
get files long
for i = 0 < files
set byte1 0x20
savepos offset1
Do
get byte1 byte
while byte1 == 0x20
savepos offset2
math offset2 - 1
goto offset2
set nsize 0x20
math offset2 - offset1
math nsize - offset2
getdstring name nsize
print %name%
get offset long
get size long
log name offset size
next i

```


it looks like they are using the renderware model format.
## Post #5
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2010-10-22T08:16:39+00:00
- Post Title: wii .arc files

> Reply from chrrox
>
> here is a quckbms script.
Code: Select allendian big
get files long
for i = 0 < files
set byte1 0x20
savepos offset1
Do
get byte1 byte
while byte1 == 0x20
savepos offset2
math offset2 - 1
goto offset2
set nsize 0x20
math offset2 - offset1
math nsize - offset2
getdstring name nsize
print %name%
get offset long
get size long
log name offset size
next i


it looks like they are using the renderware model format.

I appreciate your assistance on this difficult problem.
## Post #6
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2010-10-26T10:15:05+00:00
- Post Title: wii .arc files

> U8Tool from Howard C can handle *.arc files. You can compress and decompress them with it.
>
> 
>
> http://gbatemp.net/index.php?act=findpost&pid=1341181
