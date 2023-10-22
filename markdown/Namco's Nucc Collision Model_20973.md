## Post #1
- Username: tormunds
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Dec 11, 2015 1:52 am
- Post datetime: 2019-08-16T19:47:59+00:00
- Post Title: Namco's Nucc Collision Model

Hi, how's it going? I'm trying to understand how collisions work in Namco games (Jojo, Naruto Storm, etcetera), and I need some help with that. I have a file that controls the collision on a stage, but the weird thing is that it only contains vertex data. No faces at all. I assume it must be some kind of triangle strips, but I haven't been able to figure it out.

The file is divided in sections. Each section contains vertices and vertices only. No face data or anything else. Each vertex has X, Z, Y positions (all of them being float values, which means each vertex is 0xC bytes long).

File header:
0x0 to 0x4 multiplied by 0x24 -> Total size of file

Section 1 (0xC to 0x87B):
Header is in 0x4, and it's 0x8 bytes long.
0x4 to 0x8 multiplied by 0x24 -> Total size of section 1, measuring from the end of this section's header.
0x8 to 0xC -> Foot effect when characters step on this collision

Section 2 (0x884 to 0x125B):
Header is in 0x87C, and it's 0x8 bytes long.
0x87C to 0x880 multiplied by 0x24 -> Total size of section 2, measuring from the end of this section's header.
0x880 to 0x884 -> Foot effect when characters step on this collision

The rest of the file is basically the same. More sections until EOF.

Here's the sample file I used:
[hit model.xfbin](https://drive.google.com/file/d/143aNCoaFttgQdZKAv2tn28VB8yMTV-pi/view?usp=sharing)

Thank you in advance!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-16T21:50:08+00:00
- Post Title: Namco's Nucc Collision Model

> Reply from tormunds ↑Sat Aug 17, 2019 3:47 am at Sat Aug 17, 2019 3:47 am
>
> I have a file that controls the collision on a stage, but the weird thing is that it only contains vertex data. No faces at all. I assume it must be some kind of triangle strips, but I haven't been able to figure it out.I tried auto created "standard" triangles, no strips, and worked:
.


hitmodel.png (32.99 KiB) Viewed 88 times


(using hex2obj, view links in my sig)
## Post #3
- Username: tormunds
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Dec 11, 2015 1:52 am
- Post datetime: 2019-08-16T22:28:29+00:00
- Post Title: Namco's Nucc Collision Model

> Reply from shakotay2 ↑Sat Aug 17, 2019 5:50 am at Sat Aug 17, 2019 5:50 am
>
> 
tormunds wrote: ↑Sat Aug 17, 2019 3:47 amI have a file that controls the collision on a stage, but the weird thing is that it only contains vertex data. No faces at all. I assume it must be some kind of triangle strips, but I haven't been able to figure it out.I tried auto created "standard" triangles, no strips, and worked:
.hitmodel.png
(using hex2obj, view links in my sig)
No way! Was it really that simple? Thank you so much!

These triangles are basically just 1/2/3, 4/5/6 and so on?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-17T05:53:15+00:00
- Post Title: Namco's Nucc Collision Model

> Reply from tormunds ↑Sat Aug 17, 2019 6:28 am at Sat Aug 17, 2019 6:28 am
>
> 
These triangles are basically just 1/2/3, 4/5/6 and so on?In principle: yes.

# autocreated linear face indices (wavefront obj notation)
f 1/1 2/2 3/3 
f 4/4 5/5 6/6 
f 7/7 8/8 9/9 
...

but this includes texture faces (for "standard" meshes).

Since it's a collision mesh here
f 1 2 3 
f 4 5 6 
f 7 8 9 
...

should do.
## Post #5
- Username: tormunds
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Dec 11, 2015 1:52 am
- Post datetime: 2019-08-20T05:06:37+00:00
- Post Title: Namco's Nucc Collision Model

> Reply from shakotay2 ↑Sat Aug 17, 2019 1:53 pm at Sat Aug 17, 2019 1:53 pm
>
> 
tormunds wrote: ↑Sat Aug 17, 2019 6:28 am
These triangles are basically just 1/2/3, 4/5/6 and so on?In principle: yes.

# autocreated linear face indices (wavefront obj notation)
f 1/1 2/2 3/3 
f 4/4 5/5 6/6 
f 7/7 8/8 9/9 
...

but this includes texture faces (for "standard" meshes).

Since it's a collision mesh here
f 1 2 3 
f 4 5 6 
f 7 8 9 
...

should do.
Thank you so much! That worked perfectly!
