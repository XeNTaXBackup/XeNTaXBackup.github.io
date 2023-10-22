## Post #1
- Username: RevanCrow
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 18, 2020 9:42 pm
- Post datetime: 2020-09-14T01:13:57+00:00
- Post Title: Help with MDS files - PS4 Themes

Hi. I have a problem with a mds (text format) file for ps4
I have tried everything and it seems that it does not work with gmo
I want to convert it to a 3d model like fbx
Can someone help me find another alternative?
Link of the mds file with its texture:
[https://www.mediafire.com/download/flm4vbwb4qdi5bh](https://www.mediafire.com/download/flm4vbwb4qdi5bh)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-09-18T10:20:40+00:00
- Post Title: Help with MDS files - PS4 Themes

You'll need some coding to convert the text to a wavefront obj file for example.
From

```
			-384.000000 -12288.000000 0.000000 0.000000 0.000000 1.000000 0.000000 1.000000
                        ...

```

you'd get 
v -384.000000 -12288.000000 0.000000
vt 0.000000 1.000000
...

Face indices need a +1 each. So from 

```
0 2 3 
0 3 5 
2 6 7 
2 7 3 
6 8 9 
6 9 7 
8 11 13 
8 13 9 
5 3 14 
5 14 15 
3 7 16 
3 16 14 
7 9 17 
7 17 16 
9 13 18 
9 18 17 
15 14 10 
15 10 19 
14 16 20 
14 20 10 
16 17 4 
16 4 20 
17 18 21 
17 21 4 
19 10 22 
19 22 12 
10 20 23 
10 23 22 
20 4 24 
20 24 23 
4 21 1 
4 1 24

```
 you'd get 32 faces:
f 1 3 4
f 1 4 6
f 3 7 8
f 3 8 4
f ...

To get uvs displayed, too, faces look like so:
f 1/1 3/3 4/4
f 1/1 4/4 6/6
f 3/3 7/7 8/8
f 3/3 8/8 4/4
f ...
.
point cloud



koma-hight.png (7.92 KiB) Viewed 79 times
## Post #3
- Username: RevanCrow
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 18, 2020 9:42 pm
- Post datetime: 2020-10-14T11:53:52+00:00
- Post Title: Help with MDS files - PS4 Themes

Thank you
Is there a way to preserve the animation?
