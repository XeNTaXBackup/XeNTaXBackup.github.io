## Post #1
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-10-28T07:56:07+00:00
- Post Title: Overwatch

Hi, since today the beta of Blizzard's Overwatch came out, I was wondering if anyone had the opportunity to check what the archive format would be (CASC) ?

And if so, if it is still accessable using the CASC viewer?

T.
## Post #2
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-10-28T20:57:47+00:00
- Post Title: Overwatch

Alright, found a way to get the game installed, not for playing just to have the files to investigate 

Copy an older version of the Battle.net app over your latest version ( it does not work on the latest version ) version 6233 should do

then open a command line prompt and type int

```
battle.net.exe --game=prometheus --install
```


source : [reddit](https://www.reddit.com/r/Overwatch/comments/3qfmms/downloading_the_game_through_the_cmd_prometheus/)

It has the famous CASC files, but the current version does not support opening it, so ladislav-zezula is working on this already, as you can see in Git: [https://github.com/ladislav-zezula/CascLib](https://github.com/ladislav-zezula/CascLib)
currently looking into it so I would be able to open the files as well

Keep you posted

T.
## Post #3
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-10-29T10:38:30+00:00
- Post Title: Overwatch

Ok the CASC viewer only exports about 60 files (of the 10000 files), and the names are not resolved

One of them has a MD5 hash list that map the files to the correct names, nothing interesting yet ( most of them are dll, exe and locale files )

...

T.
## Post #4
- Username: VoliPanda
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Sep 07, 2015 4:49 am
- Post datetime: 2015-10-29T22:20:57+00:00
- Post Title: Overwatch

Way to go man!
It's a good start I guess haha

Really looking forward to this reverse-engineering.
Thanks for your effort!
And Cheers XD
## Post #5
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-10-29T23:01:11+00:00
- Post Title: Overwatch

Thanks, I'm actually waiting until something usefull drops out of the CASC viewer, like models and textures :p

So I can have some brain food to get that reverse engineered 

T.
## Post #6
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-11-04T21:37:14+00:00
- Post Title: Overwatch

THe new casc viewer has been build, the version support almost the extraction of all the files, but none of the files make a lot of sense, investigating as we speak ( or while I type  )

T.
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-11-05T00:16:15+00:00
- Post Title: Overwatch

How do you get names.
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-21T13:09:42+00:00
- Post Title: Overwatch

Well, we can try to hook hash function to get names, but one thing: main executable packed. We need unpacked variant.

btw: Who has the EXE from alpha version?
