## Post #1
- Username: Shreige
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 15, 2017 2:10 am
- Post datetime: 2021-06-27T19:24:23+00:00
- Post Title: Conception Plus: *.std.orb format

Greetings.

I'm currently attempting to rip the models from the PC version of Conception Plus, however I've run into issues doing so.

Knowing that this is similar to Zero Time Dilemma's file format, I tried the [blender 2.49 script](https://zenhax.com/viewtopic.php?t=2700), but the resulting mesh is incomplete and has no weighting.

Any help would be appreciated.

Sample: [https://anonfiles.com/V8L2y632u3/h001_zip](https://anonfiles.com/V8L2y632u3/h001_zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-27T20:09:20+00:00
- Post Title: Conception Plus: *.std.orb format

If you expect a perfect solution you'll need to wait for Mariusz Szkaradek123 to patch the script (for ZTD .std) for Conception Plus.

Another approach would be to upload a ZTD .std file so that someone could do some "debugging" to see how the scripts work.
Then hopefully the script could be patched.

Or you could try out hex2obj (view link in my sig):
.



h001_std.png (76.48 KiB) Viewed 73 times


(first sub mesh only, and: h2o doesn't care for weights)
## Post #3
- Username: Shreige
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 15, 2017 2:10 am
- Post datetime: 2021-07-02T22:15:56+00:00
- Post Title: Conception Plus: *.std.orb format

> Reply from shakotay2 ↑Mon Jun 28, 2021 4:09 am at Mon Jun 28, 2021 4:09 am
>
> 
Another approach would be to upload a ZTD .std file so that someone could do some "debugging" to see how the scripts work.
Then hopefully the script could be patched.

ZTD sample file:
[https://anonfiles.com/Xb98nc4fu5/010_zip](https://anonfiles.com/Xb98nc4fu5/010_zip)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-02T22:34:34+00:00
- Post Title: Conception Plus: *.std.orb format

Thanks, that works well:

```
D:\Blender249[ZeroTimeDilemma][PC][std][anim][2016-07-09]\010.std
======================================================================
mesh: 0 vert: 720 indice: 720 min: 0 max: 719 face: 0
mesh: 1 vert: 7182 indice: 7218 min: 0 max: 7181 face: 0
mesh: 2 vert: 100 indice: 432 min: 0 max: 99 face: 0
mesh: 3 vert: 108 indice: 108 min: 0 max: 107 face: 0
mesh: 4 vert: 25 indice: 96 min: 0 max: 24 face: 0
mesh: 5 vert: 25 indice: 96 min: 0 max: 24 face: 0
mesh: 6 vert: 30 indice: 120 min: 0 max: 29 face: 0
mesh: 7 vert: 30 indice: 120 min: 0 max: 29 face: 0
mesh: 8 vert: 1819 indice: 8370 min: 0 max: 1818 face: 0
mesh: 9 vert: 32 indice: 108 min: 0 max: 31 face: 0
mesh: 10 vert: 19491 indice: 19743 min: 0 max: 19490 face: 0
mesh: 11 vert: 4591 indice: 19743 min: 0 max: 4590 face: 0

```
Will take some time to understand how this works.
And then even more time to patch the script for Conception Plus, hopefully.

So don't expect results too soon.

edit: got a little bit further with the mesh of h001.std but didn't understand the problem with the indexing.
.



h001-std.png (12.96 KiB) Viewed 37 times
