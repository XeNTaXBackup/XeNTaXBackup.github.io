## Post #1
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-04T08:33:58+00:00
- Post Title: How to extract Busou Shinki bin file.

Hi, Guys
Somebody can make a bms script for unpacking?
I've attached one of the .bin files.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-04T12:45:52+00:00
- Post Title: How to extract Busou Shinki bin file.

Are these the full files? It sort of looks like it's...missing stuff.
## Post #3
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-04T13:07:42+00:00
- Post Title: How to extract Busou Shinki bin file.

> Reply from finale00
>
> Are these the full files? It sort of looks like it's...missing stuff.
In all, about 7.1G.
I'm uploadable after April 10th.
## Post #4
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-04-04T13:18:59+00:00
- Post Title: How to extract Busou Shinki bin file.

What game is it!?
it is using renderware game engine!?
## Post #5
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-04T13:51:02+00:00
- Post Title: How to extract Busou Shinki bin file.

> Reply from fatduck
>
> What game is it!?
it is using renderware game engine!?
Busou Shinki Battle Rondo service termination January 31, 2012.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-04T14:12:40+00:00
- Post Title: How to extract Busou Shinki bin file.

If you know any links to the client already that would be great. We should preserve resources even after they shut down.
## Post #7
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-04T14:21:55+00:00
- Post Title: How to extract Busou Shinki bin file.

> Reply from finale00
>
> If you know any links to the client already that would be great. We should preserve resources even after they shut down.
Busou Shinki have been installed in my friends PC.
## Post #8
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-04-04T16:36:45+00:00
- Post Title: How to extract Busou Shinki bin file.

Would you willing to share the all file if you don't mind?
## Post #9
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-04T16:42:39+00:00
- Post Title: How to extract Busou Shinki bin file.

> Reply from alon
>
> Would you willing to share the all file if you don't mind?
Ok, but you must one week wait for me.
## Post #10
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-05T13:58:53+00:00
- Post Title: How to extract Busou Shinki bin file.

[delete](delete)
Please give your interest.
## Post #11
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-04-06T07:27:01+00:00
- Post Title: How to extract Busou Shinki bin file.

Use this to unpack the resource:

And Please Upload The Clinet!!!

```
# http://www.busou.konami.jp/shinki_net/
# by Fatduck    Apr2012
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "PKDT"
get ver long
get BINSIZE long
get OFSRESBASE long
get NUMRES long
get OFSTBL long
for i = 0 < NUMRES
   goto OFSTBL
   get IDXSIZE long
   math OFSTBL += IDXSIZE
   get OFSRES long
   math OFSRES += 0x10
   get RESSIZE long
   get UKN long
   get RESNAME string
   log RESNAME OFSRES RESSIZE
next i
```

[Busou_test.jpg](https://xentaxbackup.github.io/file/5260_Busou_test.jpg)
## Post #12
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-06T08:07:26+00:00
- Post Title: How to extract Busou Shinki bin file.

Thanks fatduck.
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-06T08:23:38+00:00
- Post Title: How to extract Busou Shinki bin file.

Does your friend have the client? lol
I'm actually surprised I can't find the client anywhere common. It wasn't a popular game?

fatduck, can't find it on any chinese file-share hosts?
## Post #14
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-06T09:21:12+00:00
- Post Title: How to extract Busou Shinki bin file.

My friend are storing file on his PC.
In fact, file was in a state of total neglect.
## Post #15
- Username: Knights1988
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 28, 2011 12:14 pm
- Post datetime: 2012-04-12T12:13:15+00:00
- Post Title: How to extract Busou Shinki bin file.

> Reply from dj082502
>
> I promise I'll upload latest update file at  next Wednesday at farthest.
I couldn't find the client. T_T
## Post #16
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-04-12T21:49:55+00:00
- Post Title: Re: How to extract Busou Shinki bin file.

Please review the new forum rules. [viewtopic.php?f=28&t=1270](http://forum.xentax.com/viewtopic.php?f=28&t=1270)
