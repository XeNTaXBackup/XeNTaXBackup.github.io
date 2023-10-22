## Post #1
- Username: bymutou
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Nov 08, 2018 9:57 am
- Post datetime: 2020-01-05T09:18:24+00:00
- Post Title: samurai shodown 2019 model extract

I can use ue viewer to view the model, but the texture is wrong。

Sample file:[https://drive.google.com/file/d/1Bo2Q63 ... sp=sharing](https://drive.google.com/file/d/1Bo2Q63LNQcinFssqkXzpPfYuNJZqwO17/view?usp=sharing)
[1.jpg](https://xentaxbackup.github.io/file/17300_1.jpg)
## Post #2
- Username: nostalgic
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 07, 2018 11:24 am
- Post datetime: 2020-07-08T20:36:59+00:00
- Post Title: samurai shodown 2019 model extract

please i need decrypt key AES
## Post #3
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-07-08T21:19:05+00:00
- Post Title: samurai shodown 2019 model extract

> Reply from nostalgic ↑Thu Jul 09, 2020 4:36 am at Thu Jul 09, 2020 4:36 am
>
> 
please i need decrypt key AES
[https://www.gildor.org/smf/index.php?topic=6910.0](https://www.gildor.org/smf/index.php?topic=6910.0)
## Post #4
- Username: debukun13
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 29, 2011 7:13 am
- Post datetime: 2020-07-18T08:56:06+00:00
- Post Title: samurai shodown 2019 model extract

About animation file (OTRA.uexp)

1. Open it with a binary editor and delete the first part.


2. Change the extension to ".otra".

3. Open using this script.
[viewtopic.php?f=16&t=16439&start=30#p145359](https://forum.xentax.com/viewtopic.php?f=16&t=16439&start=30#p145359)

I was able to do so far, but
The position and orientation of the bone will be reversed.

Can you tell me if you know a solution?

Sorry for my poor English.
## Post #5
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-05-11T22:50:15+00:00
- Post Title: samurai shodown 2019 model extract

Here is fix for killercracker's [max script](https://forum.xentax.com/viewtopic.php?f=16&t=16439&start=30#p145359) ([download](https://drive.google.com/file/d/1_yejdcgfHhgory6BpdYcDswh5aef6LJv/view?usp=sharing)). Script is accepting _OTRA.uexp files with animations, which should be extracted from game package first.

There are many tracks which are named by their indices, I suppose they are additive animations and they're not supported by the script.




Clipboard04.jpg (107.45 KiB) Viewed 123 times
