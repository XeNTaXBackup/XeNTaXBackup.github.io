## Post #1
- Username: Reck1501
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 05, 2016 11:47 pm
- Post datetime: 2016-04-25T10:56:28+00:00
- Post Title: Paragon

So, Paragon early access has been released, and I'm currently trying to extract some files from the game, but it seems that the compression is a little different from the regular UE4 PAK files. sss
The directories and everything extracts, but the uasset files appear to be corrupted.

Has anyone managed to extract any files from the game yet?

(I could upload the archive, but it's pretty huge (11gb). The entire game is packed into one PAK file)
## Post #2
- Username: pooloo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 04, 2016 10:50 am
- Post datetime: 2016-04-27T03:41:57+00:00
- Post Title: Paragon

It is encrypted using Unreal Engine 4's built-in encryption, essentially you have to find their "secret key" to decrypt the files.
## Post #3
- Username: DarkMessiah
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 15, 2011 3:08 am
- Post datetime: 2016-05-01T02:04:06+00:00
- Post Title: Paragon

Try Umodel from gildor, according to their forum, it supports Paragon for the most part.
## Post #4
- Username: vampire775
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 09, 2015 10:00 am
- Post datetime: 2016-05-27T09:18:21+00:00
- Post Title: Paragon

> Reply from DarkMessiah
>
> Try Umodel from gildor, according to their forum, it supports Paragon for the most part.

i have try
its not work
pak must be have some change
## Post #5
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2016-08-26T12:50:35+00:00
- Post Title: Paragon

How are you currently extracting from the package?
## Post #6
- Username: lunarsythe
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 23, 2016 11:59 am
- Post datetime: 2016-08-27T23:11:13+00:00
- Post Title: Paragon

> Reply from vampire775
>
> DarkMessiah wrote:Try Umodel from gildor, according to their forum, it supports Paragon for the most part.

i have try
its not work
pak must be have some change

You're wrong, you can extract every single paragon file (at least i could), with gildor umodel, just download it and override the selection for the engine with Unreal 4.16 (if i'm not mistaken, but it's something along those lines) and it'll work, i extracted seravog for testing, warning : high AF tri count and multiple random tex groups.
## Post #7
- Username: gildor
- Rank: n00b
- Number of posts: 19
- Joined date: Tue May 25, 2010 5:15 am
- Post datetime: 2016-11-28T13:25:32+00:00
- Post Title: Paragon

PARAGON is supported by UModel. Sometimes compatibility lost, sometimes it is restored. Track this thread to get recent information:
[http://www.gildor.org/smf/index.php/topic,2902.0.html](http://www.gildor.org/smf/index.php/topic,2902.0.html)
