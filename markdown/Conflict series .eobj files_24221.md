## Post #1
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-07-11T10:52:30+00:00
- Post Title: Conflict series .eobj files

its a very old game

[https://mega.nz/file/sbhQXIIR#_4rXRVt45 ... 6lhk2K8k9k](https://mega.nz/file/sbhQXIIR#_4rXRVt45Hc79BIdcelpfynaMU_C1d7xH6lhk2K8k9k)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-11T14:57:21+00:00
- Post Title: Conflict series .eobj files

A little bit tedious to build/find the sub meshes:
.



file535-obj.png (44.93 KiB) Viewed 109 times
## Post #3
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-08-23T18:34:49+00:00
- Post Title: Conflict series .eobj files

> Reply from shakotay2 ↑Sun Jul 11, 2021 10:57 pm at Sun Jul 11, 2021 10:57 pm
>
> 
A little bit tedious to build/find the sub meshes:
.
file535-obj.png

Character model is improper.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-23T19:05:02+00:00
- Post Title: Conflict series .eobj files

> Reply from braveplayer50 ↑Tue Aug 24, 2021 2:34 am at Tue Aug 24, 2021 2:34 am
>
> Character model is improper.Surprise!  
That's what I said: "A little bit tedious to build"...
## Post #5
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-08-23T19:42:38+00:00
- Post Title: Conflict series .eobj files

Sample file: [https://mega.nz/file/MWxXEQJb#F4xUj8JUI ... NBG6xwXCMw](https://mega.nz/file/MWxXEQJb#F4xUj8JUIDkN6QGtO_ySwDjpm_0jowTXZNBG6xwXCMw)
## Post #6
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-08-24T16:11:19+00:00
- Post Title: Conflict series .eobj files

I can convert to OBJ with hex2obj or write a script
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-24T16:56:25+00:00
- Post Title: Conflict series .eobj files

Depends on your skills - but this is not a 3D format I'd suggest to start with. Looks simple on a first glance but is a little bit weird on a second.
(Watch vertex block at 0x1edf8 in the file535, FVFsize=48 and see how FFFFFFFF "wanders" after 170 vertices.)
## Post #8
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-08-27T18:11:20+00:00
- Post Title: Conflict series .eobj files

bandicam 2021-08-27 20-10-18-978.jpg (38.16 KiB) Viewed 56 times
## Post #9
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-12-10T07:23:57+00:00
- Post Title: Conflict series .eobj files

> Reply from shakotay2 ↑Sun Jul 11, 2021 10:57 pm at Sun Jul 11, 2021 10:57 pm
>
> 
A little bit tedious to build/find the sub meshes:
.
file535-obj.png

If the character models look broken due to skin weights/animations, it will be possible to write a 3ds Max/Noesis script or create a tool that will convert to an .SMD format here.
