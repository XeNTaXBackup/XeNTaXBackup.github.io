## Post #1
- Username: zzz
- Rank: beginner
- Number of posts: 21
- Joined date: Wed May 21, 2014 9:36 pm
- Post datetime: 2015-02-15T16:20:13+00:00
- Post Title: Some help interpreting model coordinates info

I'm having trouble interpreting some co-ordinates info on a model from EVE Online. Info on decals and lights for models is stored in a file like this:

[http://pozniak.pl/lmeve/ccpwgl/proxy.ph ... dn1_t1.red](http://pozniak.pl/lmeve/ccpwgl/proxy.php?fetch=dx9/model/ship/amarr/dreadnought/adn1/adn1_t1.red)

```
<flareColor json="true">[0.7921569,0.7019608,0.5450981,1.0,]</flareColor>
<spriteScale json="true">[40.0,80.0,10.0,]</spriteScale>
<name>Front_spotlight_Right_03</name>
<spriteColor json="true">[1.8154248,1.5445752,0.9077124,1.0,]</spriteColor>
<transform json="true">
[40.0129013,0.0,-0.524,0.0,7.5e-06,19.9999962,-2.92e-05,0.0,-2.0938001,0.0001,179.9765015,0.0,72.0070114,-605.2061768,290.27771,1.0,]
</transform>
<coneColor json="true">[0.3686275,0.2705882,0.1333333,1.0,]</coneColor>
</element>
```


This code is for a spotlight facing straight ahead, circled in red on the right in the pic below.

```
<flareColor json="true">[0.6431373,0.6078432,0.5411765,1.0,]</flareColor>
<spriteScale json="true">[50.0,80.0,12.0,]</spriteScale>
<name>Spotlights_Bottom_Right_01</name>
<spriteColor json="true">[0.9568627,0.9019608,0.6901961,1.0,]</spriteColor>
<transform json="true">
[0.1309239,-0.4547336,39.7398682,0.0,-39.6938515,1.9394795,0.1529686,0.0,-9.4894753,-194.0409546,-2.1891282,0.0,129.2257996,-391.4908752,50.0921898,1.0,]
</transform>
<coneColor json="true">[0.2313726,0.227451,0.2117647,1.0,]</coneColor>
</element>
```


This code is for a similar spotlight facing vertically downwards, circled in red on the left side of the pic.



I'm unable to identify which variables are responsible for the orientation of the light. I'm expecting it all to be in the Transform field.

<transform json="true">
[0.1309239,-0.4547336,39.7398682,0.0,-39.6938515,1.9394795,0.1529686,0.0,-9.4894753,-194.0409546,-2.1891282,0.0,129.2257996,-391.4908752,50.0921898,1.0,]
</transform>

The underlined are the positional co-ordinates in x-z-y format. "0.0" seems to be a break between different types of variables. The high numbers in the other groups of 3 seem to rule out the use of quaternions. I've tried plugging the numbers in and seeing which result in orientations perpendicular to each other but no luck so far.

Is there a common order of variables that matches what's in the Transform field? Thanks.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-15T21:40:16+00:00
- Post Title: Some help interpreting model coordinates info

I would set the three values
0.1309239,-0.4547336,39.7398682
to 0.0,0.0,0.0
and look what happens to the rotation of the spotlight ingame if possible.

Maybe use 1.0,1.0,1.0 since you said "0.0" is some kind of flag 
(are you sure of that? 
Resembles the w value of a matrix:
0.0
0.0
0.0
1.0)
## Post #3
- Username: zzz
- Rank: beginner
- Number of posts: 21
- Joined date: Wed May 21, 2014 9:36 pm
- Post datetime: 2015-02-15T22:46:45+00:00
- Post Title: Some help interpreting model coordinates info

Unfortunately I can not alter the ingame files.

But a dev told me it was a 4x4 transformation matrix. I've been trying conversions in matlab but no luck so far.

```
-2.1546133,0.1855232,-26.160944,0.0;
-68.5022964,29.9706249,5.8543835,0.0;
-11.8921957,102.835083,200.7899628,1.0]

[-9.7786465,24.3607254,0.0715874,0.0;
1.9348507,0.8535595,-26.1647854,0.0;
69.3824005,27.8330688,6.0387149,0.0;
11.1475887,102.8884506,200.680069,1.0]]
```


These 2 are for lights that are identical except for facing in the opposite direction along the lateral axis. Also tried altering the conversion code based on a x-z-y format instead of xyz but no luck.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-16T00:58:12+00:00
- Post Title: Some help interpreting model coordinates info

if you use the Java code from here:
[http://www.euclideanspace.com/maths/geo ... /index.htm](http://www.euclideanspace.com/maths/geometry/rotations/conversions/matrixToAngle/index.htm)
(can be transformed to C code easily)
you'll find a problem with this line
angle = Math.acos(( m[0][0] + m[1][1] + m[2][2] - 1)/2);

because ( m[0][0] + m[1][1] + m[2][2] - 1)/2
gives 7.754209 for your fst matrix
and -1.943186 for your 2nd one which is out of the range {-1.0..+1.0}

anyway, the x,y,z values are
0.611124 0.738279 -0.285434
respective
0.595484 -0.764354 -0.247311
which are mirrored vectors (is that what you mean with "opposite direction along ..."?).
Don't know what's the prob with the angle.

Doesn't make sense but if you multiply the matrix values with (PI/180.0)
you'll get this:
angle, x, y, z
1.934713 0.611124 0.738279 -0.285434
2.123733 0.595484 -0.764354 -0.247311
so the angles are very similar

(for axis angle view here:
[http://www.euclideanspace.com/maths/geo ... /index.htm](http://www.euclideanspace.com/maths/geometry/rotations/axisAngle/index.htm))
