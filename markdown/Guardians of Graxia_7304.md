## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-05T18:34:51+00:00
- Post Title: Guardians of Graxia

This is the same model format as Rise of immortals
Just a slightly different archive
[http://store.steampowered.com/app/90500/](http://store.steampowered.com/app/90500/)

[viewtopic.php?f=16&t=7303](http://forum.xentax.com/viewtopic.php?f=16&t=7303)



here is the quickbms script

```
get unk01 long
get totalheader long
get namecount long
get files long

for i = 0 < files
get nsize short
getdstring name nsize
putarray 0 i name
next i

for i = 0 < files
get unk01 long
get id long
get size long
get offset long
get nameid long
getarray NAME 0 nameid
log name offset size
next i

```

the 2nd bms script is still the same.
## Post #2
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2011-09-05T21:34:43+00:00
- Post Title: Guardians of Graxia

I'm curious, how do you decide which games you work on? They seem to be mostly japanese style games but that could just be me seeing things.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-05T21:50:11+00:00
- Post Title: Guardians of Graxia

If i play a game and like it or if i see models i may want or if i just look at a format and understand it i may work on it.
no real set order or anything.
## Post #4
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-06T12:18:30+00:00
- Post Title: Guardians of Graxia

nice one not bad, like 3d models of this game, I try investigate more is good MMORPG
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-06T14:04:47+00:00
- Post Title: Guardians of Graxia

> Reply from chrrox
>
> if i see models i may want

What do you do with the models?
