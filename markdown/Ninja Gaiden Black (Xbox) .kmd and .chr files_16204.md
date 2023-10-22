## Post #1
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2017-04-25T21:03:04+00:00
- Post Title: Ninja Gaiden Black (Xbox) .kmd and .chr files

Has anyone taken a look at these files? I was hoping to extract models and stages from this game.

[https://mega.nz/#!CtJiQYhR!q-kMCQIR7LDv ... GSLUwkS8S4](https://mega.nz/#!CtJiQYhR!q-kMCQIR7LDvN92sD13QcS4ypCAs3kd7ZGSLUwkS8S4)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-26T02:57:44+00:00
- Post Title: Ninja Gaiden Black (Xbox) .kmd and .chr files

why not try it out?



aya_a-kmd.JPG (77.63 KiB) Viewed 199 times

(many submeshes)
## Post #3
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2017-04-26T11:25:44+00:00
- Post Title: Ninja Gaiden Black (Xbox) .kmd and .chr files

I'd love to, but I'm afraid my knowledge of hex2obj is to basic.
## Post #4
- Username: guiltytrace
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2020 11:18 am
- Post datetime: 2021-07-22T01:54:37+00:00
- Post Title: Ninja Gaiden Black (Xbox) .kmd and .chr files

> Reply from shakotay2 ↑Wed Apr 26, 2017 10:57 am at Wed Apr 26, 2017 10:57 am
>
> 
why not try it out?
aya_a-kmd.JPG(many submeshes)

Hey there, can you offer a little direction on this? I was hoping mesh_viewer would help, but it doesn't recognize .kmd.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-22T07:30:47+00:00
- Post Title: Ninja Gaiden Black (Xbox) .kmd and .chr files

Hey, read the tutorial of hex2obj ('tut' button). Learn how to detect face indices and floats then research should work like a charm.
## Post #6
- Username: guiltytrace
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2020 11:18 am
- Post datetime: 2021-07-24T20:41:39+00:00
- Post Title: Ninja Gaiden Black (Xbox) .kmd and .chr files

> Reply from shakotay2 ↑Thu Jul 22, 2021 3:30 pm at Thu Jul 22, 2021 3:30 pm
>
> 
Hey, read the tutorial of hex2obj ('tut' button). Learn how to detect face indices and floats then research should work like a charm.

Just gave it a go and failed. I'll have to carve out a good bit of time to learn how to wrangle this.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-27T22:11:18+00:00
- Post Title: Ninja Gaiden Black (Xbox) .kmd and .chr files

Take your time.  

Finding the start of vertices in aya_a.kmd is no rocket science, I just scrolled down through the file in a hex editor:
.



aya_a-kmd-startOfVertices.png (23.66 KiB) Viewed 70 times
