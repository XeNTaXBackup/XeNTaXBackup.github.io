## Post #1
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2009-12-18T23:33:29+00:00
- Post Title: Borrow Hill .cxt files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-04-26T17:30:17+00:00
- Post Title: Borrow Hill .cxt files

+1 for script/editor/converter
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-26T18:19:57+00:00
- Post Title: Borrow Hill .cxt files

they are Adobe Shockwave Director files.

they can be opened with Adobe Director but I guess that for some of them it could refuse to do it because they could be protected.
Note that it doesn't mean it's a real protection/encryption, so the content is there.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-26T18:28:00+00:00
- Post Title: Borrow Hill .cxt files

anyway if someone is interested and Adobe Director doesn't want to load the files, I have a script for dumping this content and I could release it
## Post #5
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-04-26T21:03:05+00:00
- Post Title: Borrow Hill .cxt files

Oh yeah Aluigi. You were right. Files are protected.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-27T10:59:58+00:00
- Post Title: Borrow Hill .cxt files

the script will be uploaded at the following locations:
[http://aluigi.org/papers/bms/shockwave.bms](http://aluigi.org/papers/bms/shockwave.bms)

at the moment I have not uploaded it yet because there is a small bug in quickbms and so I prefer to wait the next version for releasing the script (I could release it also now because it's not a real bug but don't know, I'm thinkin about it).
## Post #7
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-04-27T20:35:05+00:00
- Post Title: Borrow Hill .cxt files

Great 
Meanwhile I have found programme called DirOpener, which can unprotect that files, so they can be easily loaded in Macromedia Director MX 2004 (newer version of Director can it load too, but game can not read them).

Thanks for pointing to Director, Aluigi
## Post #8
- Username: TanatOS
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat May 03, 2008 10:18 am
- Post datetime: 2015-01-14T21:55:43+00:00
- Post Title: Borrow Hill .cxt files

aluigi
For .dir this script dump files that shorter by 8 bytes, because
```
            math SIZE   -= 8
```
Commenting this line may help, but I don't know how it will affect on other formats.
