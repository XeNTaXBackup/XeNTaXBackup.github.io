## Post #1
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2021-06-09T20:19:45+00:00
- Post Title: No More Heroes .bin Compression

Can someone tell what kind of compression used in these files?

```
0x04 - Compressed Size
0x08 - Compressed Data
```

[Examples](https://drive.google.com/file/d/1m5N-jdY03IJUFBEVeUwiaUBsDrh0W6wz/view?usp=sharing)
## Post #2
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2021-06-10T15:11:46+00:00
- Post Title: No More Heroes .bin Compression

Solved. WOLF algorithm.

```
get ZSIZE asize
set SIZE long 0
if SIZE <= 0
    math SIZE = ZSIZE
    math SIZE *= 20
endif
comtype WOLF
string NAME p "%s.%s" NAME RSL
clog NAME 0 ZSIZE SIZE
```
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-06-10T21:03:23+00:00
- Post Title: No More Heroes .bin Compression

Nice. How did you solve it?
## Post #4
- Username: Giza
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 22, 2018 2:51 pm
- Post datetime: 2021-06-11T04:05:29+00:00
- Post Title: No More Heroes .bin Compression

> Reply from ikskoks ↑Fri Jun 11, 2021 5:03 am at Fri Jun 11, 2021 5:03 am
>
> 
Nice. How did you solve it?
brute force
## Post #5
- Username: DearP
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 01, 2023 9:23 pm
- Post datetime: 2023-03-01T13:26:30+00:00
- Post Title: No More Heroes .bin Compression

Hi man, I want to make a patch for no more heroes in my language, can you help me if you have time?
