## Post #1
- Username: Napaleon961
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 28, 2019 1:18 am
- Post datetime: 2019-01-27T18:59:26+00:00
- Post Title: how to packing games resources in game

Hi everyone,
there is an unpacking script

```
get unk01 long
get files long
for i = 0 < files
getdstring name 0x80
get offset long
get size long
log name offset size
next i

```

(taken from the forum)
I want to make a modification to the game Ascension to the Throne.
The size of the modification is much larger therefore reimport is not suitable.
please, help, forum.

Resource1.pak
[https://ufile.io/20rb0](https://ufile.io/20rb0)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2019-01-27T21:48:29+00:00
- Post Title: how to packing games resources in game

"reimport2" mode in quick bms may help you to pack larger archive.
## Post #3
- Username: Napaleon961
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 28, 2019 1:18 am
- Post datetime: 2019-01-28T17:55:31+00:00
- Post Title: how to packing games resources in game

> Reply from ikskoks
>
> "reimport2" mode in quick bms may help you to pack larger archive.
thanks, I will check
