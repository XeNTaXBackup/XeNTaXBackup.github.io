## Post #1
- Username: jizames
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Aug 10, 2012 5:51 pm
- Post datetime: 2012-09-08T02:54:27+00:00
- Post Title: pxp archive files?

Headers all show PX.Í in the first 4 bytes. Filenames are shown shortly after, just not sure how to go about extracting them. [http://www.mediafire.com/?d3xzat0mmjlkbi9](http://www.mediafire.com/?d3xzat0mmjlkbi9)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-08T06:26:23+00:00
- Post Title: pxp archive files?

What game is it
## Post #3
- Username: jizames
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Aug 10, 2012 5:51 pm
- Post datetime: 2012-09-08T09:26:56+00:00
- Post Title: pxp archive files?

> Reply from finale00
>
> What game is it

Zen Pinball. Want to gut the music out of the tables, which are mp3s from the looks of it.
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-09-08T19:35:28+00:00
- Post Title: pxp archive files?

filename parser. useless.

```
goto 12
get files long
get filetablesize long
goto 40
for f = 0 < files
  get a long
  get b long
  get fancy_f char
  get strlen char
  getdstring str strlen
  padding 4
  get unknown long
  print "%str%"
next f

print "Finished"

```
## Post #5
- Username: jizames
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Aug 10, 2012 5:51 pm
- Post datetime: 2012-09-09T04:52:26+00:00
- Post Title: pxp archive files?

> Reply from WRS
>
> filename parser. useless.
Code: Select allidstring "PX"
goto 12
get files long
get filetablesize long
goto 40
for f = 0 < files
  get a long
  get b long
  get fancy_f char
  get strlen char
  getdstring str strlen
  padding 4
  get unknown long
  print "%str%"
next f

print "Finished"
So no easy way to pull the tracks out of the archives via a bms script?
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-09T06:38:37+00:00
- Post Title: pxp archive files?

I'm assuming he meant this thing only contains names and no actual data.
## Post #7
- Username: jizames
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Aug 10, 2012 5:51 pm
- Post datetime: 2012-09-09T09:03:48+00:00
- Post Title: pxp archive files?

> Reply from finale00
>
> I'm assuming he meant this thing only contains names and no actual data.
Oh, I just supplied one of the tiniest files to see if it would be enough for some progress. I'm pretty positive the data's buried somewhere in this: [http://www.mediafire.com/?yeugfw7uckj74s4](http://www.mediafire.com/?yeugfw7uckj74s4)
## Post #8
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-09-09T13:25:10+00:00
- Post Title: pxp archive files?

i meant my script was useless. you can easily parse the filenames, but the data is encrypted or compressed somehow.

there is all kinds of data in the last archive posted:

> sfx/wate_001.mp3 2541926 71117 64331
>
>   sfx/you_win.mp3 9688207 42904 38249
>
>   sfx/zangief_bonus.mp3 9726456 146349 139543
>
>   table_logo_v12.png 38353548 26839 25619

there are also some duplicate files which share the same offets/sizes. to extract the data:

```
goto 12
get files long
get filetablesize long
goto 40

for f = 0 < files
  get a long   # info pntr
  get b long    # assumed size
  get fancy_f char
  get strlen char
  getdstring str strlen
  padding 4
  get unknown long   # zsize
  math totsize += unknown
  print "%str% %a% %b% %unknown%"
  log str a unknown # <<
next f

print "Finished"

```
## Post #9
- Username: jizames
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Aug 10, 2012 5:51 pm
- Post datetime: 2012-09-10T08:47:22+00:00
- Post Title: pxp archive files?

Damn, so is it an unknown compression? It looked like it would be a breeze but I'm guessing it's better to give up hope on accessing those files. The entire game is loaded with those pxp files, so I guess they wanted to make sure no one tampered with them.
