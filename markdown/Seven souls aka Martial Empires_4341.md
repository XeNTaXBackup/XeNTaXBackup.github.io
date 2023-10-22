## Post #1
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-04-17T01:23:12+00:00
- Post Title: Seven souls aka Martial Empires

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-17T13:29:04+00:00
- Post Title: Seven souls aka Martial Empires

I have seen no info-table in them so the only way to extract the files is through offzip that works perfectly with these archives:
offzip -a archive.vfs c:\output_folder 0
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-17T14:49:54+00:00
- Post Title: Seven souls aka Martial Empires

silly pixellegolas don't forget to include the file table.


```
#from chrrox and aluigi
open FDDE VFS 0
open FDDE INF 1

get id longlong 1
get files long 1
goto 0x48 1
for i = 0 < files
    getdstring name 0xD8 1
    get ZIPPED long 1
    get DUMMY long 1
    get offset longlong 1
    get zsize longlong 1
    get size longlong 1
    get TIMESTAMP longlong 1
    get TIMESTAMP longlong 1
    get TIMESTAMP longlong 1
    if ZIPPED == 0
        log name offset zsize
    else
        clog name offset zsize size
    endif
next i


```
## Post #4
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-04-17T15:09:33+00:00
- Post Title: Seven souls aka Martial Empires

strange stuff, I tried offzip yesterday and wrote exactly the same as now but it suddenly works!? Was I tired or the comp?
## Post #5
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-04-17T15:27:14+00:00
- Post Title: Seven souls aka Martial Empires

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-17T19:37:21+00:00
- Post Title: Seven souls aka Martial Empires

hmm this format does not look to bad
## Post #7
- Username: cyril81
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 25, 2010 12:38 am
- Post datetime: 2010-09-24T16:40:36+00:00
- Post Title: Seven souls aka Martial Empires

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-24T21:17:07+00:00
- Post Title: Seven souls aka Martial Empires

i made a 3ds max importer.
## Post #9
- Username: cyril81
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 25, 2010 12:38 am
- Post datetime: 2010-09-25T13:53:16+00:00
- Post Title: Seven souls aka Martial Empires

> Reply from chrrox
>
> i made a 3ds max importer.

is there any chance to send me the importer please?
## Post #10
- Username: bmobius
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 18, 2010 6:44 am
- Post datetime: 2010-10-07T06:43:58+00:00
- Post Title: Seven souls aka Martial Empires

I too wouldn't mind that Max importer, if it's not too much a hassle? If so, no worries!
## Post #11
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2010-10-25T10:55:21+00:00
- Post Title: Seven souls aka Martial Empires

May I ask you one thing, chrrox ?
How did you assign the texture to the mesh ?
I could not find a material information or texture information in .msh file.
## Post #12
- Username: kpanic
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 05, 2011 5:16 pm
- Post datetime: 2011-02-06T09:52:17+00:00
- Post Title: Seven souls aka Martial Empires

hi, sorry for bump this old post, but im working on a fansite of this game and want to make some renders for it, i have the client extracted but i cant use the msh files.

chrrox can you tell me or help a bit with them? can you share ur 3d max importer?

Thanks in advance
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-03-28T02:20:35+00:00
- Post Title: Seven souls aka Martial Empires

Ok ill release an update soon i got this format figured out now.
[7stree1.png](https://xentaxbackup.github.io/file/4124_7stree1.png)
## Post #14
- Username: kpanic
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 05, 2011 5:16 pm
- Post datetime: 2011-06-06T09:33:04+00:00
- Post Title: Seven souls aka Martial Empires

> Reply from chrrox
>
> Ok ill release an update soon i got this format figured out now.

Hi chrrox really nice work, when you go to release it?

I cant wait, i want to make some cool renders for a fan page of this game
## Post #15
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-06T11:05:51+00:00
- Post Title: Seven souls aka Martial Empires

I already did
[viewtopic.php?f=16&t=6337&p=54582&hilit ... uls#p54582](http://forum.xentax.com/viewtopic.php?f=16&t=6337&p=54582&hilit=seven+souls#p54582)
