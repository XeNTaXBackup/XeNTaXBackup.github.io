## Post #1
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2011-08-22T00:37:06+00:00
- Post Title: Deep Black Game Localization File (global.pack)

Can anyone help me to unpack/repack this files please?

[http://www.multiupload.com/865V94V1G6](http://www.multiupload.com/865V94V1G6)
## Post #2
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2011-08-23T10:33:36+00:00
- Post Title: Deep Black Game Localization File (global.pack)

Hi
I made a quickbms script for unpack

```
get EXTNUM long
get EXTOFF long
get FILES long
get NAMESOFF long
for k = 0 < EXTNUM
goto EXTOFF
getdstring EXT 0X4
get FIRST long
get NUM long
math NUM += FIRST
goto NAMESOFF
for i = FIRST < NUM
getdstring NAME 0X20
get OFFSET long
get SIZE long
string NAME += "."
string NAME += EXT
log NAME OFFSET SIZE
next i
math EXTOFF += 0xc
savepos OFF
set NAMESOFF = OFF
next k

```
## Post #3
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2011-08-25T11:54:27+00:00
- Post Title: Deep Black Game Localization File (global.pack)

Thanks for reply 

But how can I repack unpacked files ?
## Post #4
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-08-30T00:43:54+00:00
- Post Title: Deep Black Game Localization File (global.pack)

This game has english version?
## Post #5
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2011-09-04T22:47:29+00:00
- Post Title: Deep Black Game Localization File (global.pack)

No. German version.
## Post #6
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-09-05T23:34:01+00:00
- Post Title: Deep Black Game Localization File (global.pack)

> Reply from oyunceviri
>
> No. German version.
Unfortunate...
## Post #7
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-10-21T12:11:08+00:00
- Post Title: Deep Black Game Localization File (global.pack)

Maybe someone still need it.
There is tool for bsrt file, and to insert text files (loc,bsrt) back to the pack file. [http://www.sendspace.com/file/oj40hr](http://www.sendspace.com/file/oj40hr)
## Post #8
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2012-10-25T16:35:50+00:00
- Post Title: Deep Black Game Localization File (global.pack)

Great tool. Thanks bro
## Post #9
- Username: bero
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Dec 27, 2010 1:05 am
- Post datetime: 2012-12-24T19:42:18+00:00
- Post Title: Deep Black Game Localization File (global.pack)

Maybe someone still need it.
There is tool for generate and replace font.

download: [https://sites.google.com/site/gamelocal ... ects=0&d=1](https://sites.google.com/site/gamelocalize/files/deepblack_jp.zip?attredirects=0&d=1)
screenshot: [http://gamelocalize.blogspot.jp/2012/12 ... -demo.html](http://gamelocalize.blogspot.jp/2012/12/deep-black-reloaded-demo.html)

document written in Japanese, see source.
## Post #10
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2012-12-26T11:56:00+00:00
- Post Title: Deep Black Game Localization File (global.pack)

Thanks bro
