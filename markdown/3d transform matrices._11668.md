## Post #1
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2014-07-07T07:22:39+00:00
- Post Title: 3d transform matrices.

4x4 matrix format

How would a basic translation, scale/rotation matrix look like ( before they are multiplied together).

Like if you want to move the object x 10f, y10f, z10f

how would you specify it in the matrix:
1  0  0  0
0  1  0  0
0  0  1  0
0  0  0  1

you have 16 values per matrix.
## Post #2
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-07-07T19:16:24+00:00
- Post Title: 3d transform matrices.

The best thing to do is to have the different positions and rotations already stated and then convert them all into a transformation

It's not all about putting numbers here and there, it's a whole calculation.

If you are working in MS for example you can do this to have a transformation matrix

```
tfm = matrix3 0

tfm.rotationpart = Quat
tfm.rotationpart = eulerangles -- if you are working with the system 3DS uses to rotate which is only 3 values instead of 4.

tfm.translationpart = Point3

tfm.scalerotationpart = Quat

tfm.scalepart = Point3

```


You can't really calculate a TFM by yourself.

Which program are you using? they usually have premade calculations for the TFM.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-07-07T20:57:17+00:00
- Post Title: 3d transform matrices.

> Reply from djmauro
>
> Like if you want to move the object x 10f, y10f, z10f
From the wiki ([http://en.wikipedia.org/wiki/Translation_%28geometry%29](http://en.wikipedia.org/wiki/Translation_%28geometry%29)):
[](http://www.pic-upload.de/view-23817257/3D-translation.jpg.html)
(With 10f expected to be 10.0 (?) vx, vy, vz would be set to 10.0 each.)

But as Seyren mentioned: "it's a whole calculation" since a 3D object
usually consists of many vectors pn. So I would suggest you to consider the use
of a 3D program (blender, 3dsmax, Noesis) where you could try to move a cube by script for example.

btw "homogeneous" coordinate: as far as I remember it simply means to expand a 3 dimensional vector by a 4th element (the '1').
## Post #4
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2014-07-08T01:34:03+00:00
- Post Title: 3d transform matrices.

its about trying to manipulate existing model that toes not have any kind of exporter that ( so cant do that in 3d etc) - but in game its often ether too large or rotated at a wrong angle - so would need some matrix manipulation.

And for example static mesh like .obj doesn't have any matrix info. So if i at some poitn create the converter and it works - id still have the problem of not being able to change the  matrices.
## Post #5
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-07-08T01:52:09+00:00
- Post Title: 3d transform matrices.

If what you mean is to change it in-game i suggest you to get the transformation in a program, get the values, change them and calculate it again, and then put it in the file.

The only values that are actually changable are the position, which are in the last row  of the TFM (At least they are on the format i'm currently working on), The three position coordinates were put like this:

```
0 1 0 0
0 0 1 0
5 3 2 1

```

Being 5 the x coord, 3 the z coord, and 2 the y coord (The engine was using the same coordinates like maya, Y as height.)

However the rest of the stuff was a total math calculation, the whole thing is in the D3D classes of C++ but i still think getting the job done somewhere else is a better idea.
## Post #6
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-07-08T07:02:09+00:00
- Post Title: 3d transform matrices.

The layout of the matrix will be transposed between row major and column major. But in any case, in this context, it's easiest to think of it as a point in space with 3 axes, forward, right and up. Each of those axes would typically be a normalized vector. It's easy enough to determine a direction in space and say that's your forward axis, but then deriving up/right is also necessary, which makes it impossible to describe a proper rotation with a single vector. (even though you could make assumptions about your right/up vectors to produce an orthogonal matrix from a single vector)

Of course, a transform matrix isn't bound inherently to these properties, so it may be non-uniformly scaled or skewed to be non-orthogonal. You should first try to understand how a rotation matrix is constructed from Eulee/radians. Google "Euler to matrix" and find the implementation/explanation that's easiest on your brain.
