## Post #1
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2011-11-20T04:18:45+00:00
- Post Title: A Treehouse of My Own .fmv and .xni

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2011-11-29T01:48:31+00:00
- Post Title: A Treehouse of My Own .fmv and .xni

Hey, is anyone interested in helping me with this?
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-12-01T08:40:35+00:00
- Post Title: A Treehouse of My Own .fmv and .xni

xni is just an ini-style config

the fmv files are animation frames. i dont think you will be able to do anything with them though

```

get P_TABLE long
get DUMMY long
get DUMMY long
get FRAMES long
get DUMMY long
get WIDTH long # ?
get HEIGHT long # ?
get BBP long # ?

math USIZE = WIDTH
math USIZE *= HEIGHT
math USIZE *= 4 # maybe BBP as bytes?

goto P_TABLE

get BNAME basename

for f = 0 < FRAMES
  get DUMMY long # 1
  get DUMMY long # 4
  get SIZE long
  get PNTR long
  savepos NXT
  math NXT += 32 # skip unknown

  goto PNTR
  get DUMMY long # static identifier ??
  
  savepos FMVPOS

  string NAME p= "%s_frame_%03i" BNAME f
  clog NAME FMVPOS SIZE USIZE

  goto NXT
next f

```
## Post #4
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2011-12-01T23:56:31+00:00
- Post Title: A Treehouse of My Own .fmv and .xni

> Reply from WRS
>
> xni is just an ini-style config

the fmv files are animation frames. i dont think you will be able to do anything with them though

I guess so, as it also turned out a series of somewhat unreadable files that have to be deciphered, too.
## Post #5
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2011-12-27T13:10:12+00:00
- Post Title: A Treehouse of My Own .fmv and .xni

The contents of this post was deleted because of possible forum rules violation.
