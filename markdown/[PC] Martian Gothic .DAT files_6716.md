## Post #1
- Username: MiLOxentax
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 26, 2010 10:39 am
- Post datetime: 2011-06-03T06:41:04+00:00
- Post Title: [PC] Martian Gothic .DAT files

Hello. 

I happen to be a fan of (what now can be considered) old-school pre-rendered backgrounds.
And this game is a great example of such technique, with some very well designed environments.

So I've been trying to find the right tools to open/extract the contents of the .dat files, where I believe the background images should be... but so far had no luck.

Could someone please take a look at them and maybe will figure it out. I know it's a rather common archive type, especially for a PC title, but being a noob at this stuff, I couldn't access the inside files of it and get the properly viewable pictures.

Any help would be really appreciated.

Here are 3 sample .dat files from [cameras] folder.

[http://www.mediafire.com/?5rcmbtb056a9t4b](http://www.mediafire.com/?5rcmbtb056a9t4b)
## Post #2
- Username: MiLOxentax
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 26, 2010 10:39 am
- Post datetime: 2011-10-14T20:17:33+00:00
- Post Title: [PC] Martian Gothic .DAT files

Bump. Can someone at least have a look and let me know that it can not be done.
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-16T08:17:25+00:00
- Post Title: [PC] Martian Gothic .DAT files

in the dat files you posted the header contains a bunch of floats, followed by some integers. i highly doubt these files contain image data. doesn't look like image data to me.

This is not image data.

```
9
75.8975
10.2599

-252.189
80.4337
8.98439
-241.153

75.9379
11.2542
-252.091
32.79

17.9
0
0
0

0
0
0
0

6
0
20
0

0
0
0
0

0
5
0
0

0
0
0
19

19
3
0
0

0
0
0
14

```
## Post #4
- Username: Preddy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 14, 2010 7:45 pm
- Post datetime: 2015-10-24T18:04:57+00:00
- Post Title: [PC] Martian Gothic .DAT files

*.dat files really contains background (by offset 0x240) in 16 bit format. Here is sample:
[https://drive.google.com/file/d/0B8NDId ... NsSDQ/view](https://drive.google.com/file/d/0B8NDIdEGtVsXX3ZIZlRrNTNsSDQ/view)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-24T20:06:53+00:00
- Post Title: [PC] Martian Gothic .DAT files

use irfanview:



cam1_dat.JPG (134.3 KiB) Viewed 72 times
