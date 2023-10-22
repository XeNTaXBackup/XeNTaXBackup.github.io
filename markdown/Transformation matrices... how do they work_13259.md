## Post #1
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-08-30T02:33:12+00:00
- Post Title: Transformation matrices... how do they work?

Hi everyone,

This is more general 3D format questions.  I'm having problems getting bits and pieces of models into the right place, and it's because I don't quite know how to parse a transformation matrix to find the proper location and rotation for a given part.  Let me start with some simple examples.

Transformation:   
1.0000000  0.0000000  0.0000000  0.0000000
                         0.0000000  1.0000000  0.0000000  0.0000000
                         0.0000000  0.0000000  1.0000000  0.0000000
                         0.0000000  0.0000000  0.0000000  0.0000000

This is a simple one!  Rotation should be the diagonal (m11, m22, m33).  Transpose is the bottom row (m41, m42, m43).  Column 4 is... well, I've only seen zeroes there, so it's probably surplus data.  The upper left 3x3 is *probably* a rotational matrix, but... let's move on.  The object associated with this matrix will be at (0,0,0), scaled (1,1,1) in each direction, and have no rotation.  EZPZ.

Ok, let's try something a bit more complicated.

Transformation:   
1.0000000  0.0000000  0.0000000  0.0000000
                         0.0000000  1.0000000  0.0000000  0.0000000
                         0.0000000  0.0000000  1.0000000  0.0000000
                         7.0842280  75.2871800  0.0000000  0.0000000

Oh shit!  Ok, the rotation diagonal is still easy to see.   (1,1,1), right down the diagonal.  And the bottom row... that's the transform.  So the object is 7.084 in the x direction, 75.2871800 in the y direction, and 0 in the z.  Ok, this is Cryengine, so divide those by 100 for some really weird, esoteric random reason.  (.07084, .75287, 0).  Not too bad!  Still EZPZ.

Transformation:   
1.0000000  0.0000000  0.0000000  0.0000000
                         0.0000000  -1.0000000  -0.0000002  0.0000000
                         0.0000000  0.0000002  -1.0000000  0.0000000
                         0.0000000  0.0000000  -0.0000038  0.0000000

Err... ok, fuck.  There are minus signs here on the rotation diagonal.  Now... is that a rotation diagonal?  I'm not so sure anymore.  Is -1 90 degrees or 180 degrees?  I'm thinking...sine or cosine?  At least the transform is easy, aside from rounding errors.  

Transformation:    
0.0767598  0.1049622  0.9915094  0.0000000
                         -0.9960693  0.0521773  0.0715892  0.0000000
                         -0.0442203  -0.9931072  0.1085546  0.0000000
                         -8.8380730  15.5654300  -96.0408500  0.0000000

Ok.  I'm officially fucked.  What the hell does this mean?  How do I apply this to a vertex to figure out where it actually goes?
## Post #2
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2015-08-30T06:06:03+00:00
- Post Title: Transformation matrices... how do they work?

Actually the math behind matrices is not as hard. What you usually need is just multiply your 4x4 matrix by your vector without bothering about what's in it.
[https://open.gl/transformations](https://open.gl/transformations) and [https://www.opengl.org/archives/resourc ... ations.htm](https://www.opengl.org/archives/resources/faq/technical/transformations.htm) can give you an idea.

Also note that sometimes matrices are inverted.
## Post #3
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-08-30T13:32:39+00:00
- Post Title: Transformation matrices... how do they work?

> Reply from RoadTrain
>
> Actually the math behind matrices is not as hard. What you usually need is just multiply your 4x4 matrix by your vector without bothering about what's in it.
https://open.gl/transformations and https://www.opengl.org/archives/resourc ... ations.htm can give you an idea.

Also note that sometimes matrices are inverted.

Ok, that helped a bunch.  I think the algorithms in my exporter program is a lot more solid now, although some positions still end up... not quite where they should be.  Rotated 180 degrees, off by 1.4 in the x direction.  But, there is probably some weird parent/child relationship thing going on here that I still need to figure out.  At least all the parts within that child and below are all in the proper position relative to each other.

Cryengine:  Making everything hard since forever.  (Honestly though, it's probably a bug in my recursive function call...)
## Post #4
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2015-08-30T20:00:28+00:00
- Post Title: Transformation matrices... how do they work?

Also some interesting read on row-order and column-order matrices
[https://fgiesen.wordpress.com/2012/02/1 ... n-vectors/](https://fgiesen.wordpress.com/2012/02/12/row-major-vs-column-major-row-vectors-vs-column-vectors/)

If we look at the examples from open.gl, the translation part is stored in the 4th column, while in your case it is in the 4th row.
Depending on how you calculate matrix product, you may want to transpose your matrix before multiplying. Also don't forget that matrix product operation is non-commutative, so the order matters.
## Post #5
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-08-31T00:48:51+00:00
- Post Title: Transformation matrices... how do they work?

> Reply from RoadTrain
>
> Also some interesting read on row-order and column-order matrices
https://fgiesen.wordpress.com/2012/02/1 ... n-vectors/

If we look at the examples from open.gl, the translation part is stored in the 4th column, while in your case it is in the 4th row.
Depending on how you calculate matrix product, you may want to transpose your matrix before multiplying. Also don't forget that matrix product operation is non-commutative, so the order matters.

The thing that is causing me problems is there are about 140 objects in the file I'm working with, and 90% of them are in the right place.  And some of the children of a parent that is clearly in the wrong place are still right relative to the parent.  It's easy to fix manally, but... who wants to manually fix something like this? 

I'll have to post the examples to show what's going on.  It's just weird.
