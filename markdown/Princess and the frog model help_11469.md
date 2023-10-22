## Post #1
- Username: evamay222
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 06, 2014 9:41 pm
- Post datetime: 2014-04-30T05:36:03+00:00
- Post Title: Princess and the frog model help

Could anyone help me extract the models from this game please?
[king_maldonia.7z](https://xentaxbackup.github.io/file/7279_king_maldonia.7z)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-30T08:25:02+00:00
- Post Title: Princess and the frog model help

using hex2obj (view link in my sig):



king_mal.JPG (87.3 KiB) Viewed 136 times
## Post #3
- Username: evamay222
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 06, 2014 9:41 pm
- Post datetime: 2014-04-30T16:59:00+00:00
- Post Title: Princess and the frog model help

Thank you.Two things,first can i use the same settings for every model in the game? And two, the face is missing.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-24T08:10:12+00:00
- Post Title: Princess and the frog model help

> Reply from evamay222
>
> Thank you.Two things,first can i use the same settings for every model in the game?
For few games the startaddress for vertices is the same but in general it is different. Vertices count and the two params for go1 are variable.
(There's a tutorial button ("tut") in hex2obj.)

> And two, the face is missing.weird. I perform a quick check of models only. Don't have the time to do the time consuming part, sry.

edit: about 100 triangles are wrong. To correct this I used a modified TriStrips algo:
[king_maldonia_triAlt.zip](http://www.uploadmb.com/dw.php?id=1398904647)

edit: the movie.res you uploaded contains shockwave files. I downloaded 1.3 MB only
but I guess there are no model's faces (vertices), just pics and gui resources.
Here's a swf-pic for example:



0x8B00.JPG (41.94 KiB) Viewed 82 times
