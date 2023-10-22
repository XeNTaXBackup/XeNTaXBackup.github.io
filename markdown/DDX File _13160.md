## Post #1
- Username: Codec
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Aug 18, 2014 7:57 pm
- Post datetime: 2015-08-06T16:15:16+00:00
- Post Title: DDX File ?

Hi guys.

Fallout 3 .ddx texture file for export and import, waiting for your help.

Thank you in advance.
[hairghoul01.rar](https://xentaxbackup.github.io/file/9489_hairghoul01.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-07T13:33:11+00:00
- Post Title: DDX File ?

> Reply from Codec
>
> [...], waiting for your help.yep. Seems that's nowadays forum members most preferred job.  
Having done some forum search for 'ddx' you'd have got 7 matches with one of them ([viewtopic.php?f=18&t=6872&p=55929&hilit=ddx#p55929](http://forum.xentax.com/viewtopic.php?f=18&t=6872&p=55929&hilit=ddx#p55929)) telling you this:

> So, as far as I can tell, all DDX files are two DDS files sharing the same header that are compressed separately (sans header) using something similar to ZLIB and then concatenated into one file.
The reversing result is this:


hairghoul.JPG (119.28 KiB) Viewed 77 times



Use offzip for decompressing then apply DXT5 headers with the suiting values for width/height.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-08-08T20:14:38+00:00
- Post Title: DDX File ?

"waiting for your help".   How about you do *some* research yourself. Also, why do you need the help, what are you going to do with it?
