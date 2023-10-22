## Post #1
- Username: DarkAngel
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jan 23, 2011 12:12 pm
- Post datetime: 2011-01-23T15:52:42+00:00
- Post Title: (PC) Elements of War (.pak)

Please help me unpack the game files.
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-01-23T16:41:53+00:00
- Post Title: (PC) Elements of War (.pak)

Nobody can help without sample of file.
## Post #3
- Username: DarkAngel
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jan 23, 2011 12:12 pm
- Post datetime: 2011-01-23T17:50:48+00:00
- Post Title: (PC) Elements of War (.pak)

file is too big offer cut file

[http://www9.zippyshare.com/v/61906673/file.html](http://www9.zippyshare.com/v/61906673/file.html)
## Post #4
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-01-23T19:57:42+00:00
- Post Title: (PC) Elements of War (.pak)

I can see file structure on the start and then goes all the files packed with zlib. But that's all what I can do :/
## Post #5
- Username: DarkAngel
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jan 23, 2011 12:12 pm
- Post datetime: 2011-01-24T19:39:49+00:00
- Post Title: (PC) Elements of War (.pak)

Script or program who can do something and then something goes wrong. I am not strong. I would be very grateful.
## Post #6
- Username: Fenris93
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Jul 20, 2010 6:51 am
- Post datetime: 2011-04-22T02:56:29+00:00
- Post Title: (PC) Elements of War (.pak)

Anoyone knows something new about it?
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-22T08:10:06+00:00
- Post Title: (PC) Elements of War (.pak)

the sample no longer exist
## Post #8
- Username: Fenris93
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Jul 20, 2010 6:51 am
- Post datetime: 2011-04-22T12:57:15+00:00
- Post Title: (PC) Elements of War (.pak)

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-22T13:37:36+00:00
- Post Title: (PC) Elements of War (.pak)

script for quickbms:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "SMA"
get DUMMY byte
get DUMMY byte
get FILES long
get HEAD_SIZE long
for i = 0 < FILES
    get NAME string
    get SIZE long
    get ZSIZE long
    get OFFSET long
    if ZSIZE == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #10
- Username: Fenris93
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Jul 20, 2010 6:51 am
- Post datetime: 2011-04-22T13:41:58+00:00
- Post Title: (PC) Elements of War (.pak)

That was quick   Thank you very much, you're the best.
## Post #11
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-05-12T05:42:13+00:00
- Post Title: (PC) Elements of War (.pak)

And how to pack these files again?
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-05-17T13:20:19+00:00
- Post Title: (PC) Elements of War (.pak)

quickbms with the same script can reinject too.
a step-by-step example is available here:
[viewtopic.php?p=52546#p52546](http://forum.xentax.com/viewtopic.php?p=52546#p52546)
